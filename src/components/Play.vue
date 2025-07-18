<template>
    <audio ref="audioPlayer" :src="audioSource"></audio>
    <button @click="togglePlay" class="play flex-c ai-c" style="margin-bottom: 30px;">
        <img :src="isPlaying ? pauseIcon : playIcon"
        width="60px" alt="play">
        <h2 class="fs-40 color-white">
            {{ isPlaying ? 'Pause' : 'Play' }}
        </h2>
    </button>
</template>
<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const audioPlayer = ref(null);
const audioSource = ref('/audio/track.mp3'); // ¡Cambia esta ruta!
const isPlaying = ref(false);

import playIcon from '../assets/icons/play.svg'; // Asegúrate que esta ruta sea correcta desde tu .vue
import pauseIcon from '../assets/icons/pause.svg';

const togglePlay = () => {
  if (isPlaying.value) {
    audioPlayer.value.pause();
  } else {
    audioPlayer.value.play()
      .catch(error => {
        console.error('Error al reproducir:', error);
        alert('No se pudo reproducir.');
      });
  }
};

onMounted(() => {
  if (audioPlayer.value) {
    audioPlayer.value.addEventListener('play', () => isPlaying.value = true);
    audioPlayer.value.addEventListener('pause', () => isPlaying.value = false);
    audioPlayer.value.addEventListener('ended', () => isPlaying.value = false);
  }
});

onUnmounted(() => {
  if (audioPlayer.value) {
    audioPlayer.value.pause(); // Pausar al desmontar para limpiar
    // No es estrictamente necesario remover los listeners para refs simples,
    // Vue los limpia en onUnmounted, pero es buena práctica en setups complejos
  }
});
</script>