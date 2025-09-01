<template>
    <div class="timer">
        <p>{{ formattedTime }}</p>
    </div>

</template>
<script setup>
import {ref, computed, onMounted, onBeforeMount} from 'vue';

const targetTime = new Date("2025-10-04T23:59:59").getTime();
const currentTime = ref(new Date().getTime());
const timeRemaining = ref(targetTime - currentTime.value);

const formattedTime = computed(()=>{
    const seconds = Math.floor(timeRemaining.value / 1000);
    const minutes = Math.floor(seconds / 60);
    const hours = Math.floor(minutes / 60);
    const days = Math.floor(hours / 24);

    return `${days}d ${hours % 24}h ${minutes % 60}m ${seconds % 60}s`;
});


let intervalId;

onMounted(() => {
    intervalId = setInterval(updateTimer, 1000);
});
onBeforeMount(()=>{
    clearInterval(intervalId)
});

function updateTimer(){
    currentTime.value= new Date().getTime();
    timeRemaining.value= Math.max(0,targetTime-currentTime.value);
}

</script>