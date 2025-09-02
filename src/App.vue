<script setup>
import Timer from './components/Timer.vue';
import Play from './components/Play.vue';

import { ref, computed, onMounted, onUnmounted } from 'vue';
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

//const animatedElement= ref(null);

onMounted(() => {
  // Fade + slide-up
  const items = document.querySelectorAll('.animatedItem');
  items.forEach((item, index) => {
    gsap.fromTo(
      item,
      {
        opacity: 0,
        y: 50
      },
      {
        opacity: 1,
        y: 0,
        duration: 0.8,
        ease: 'power4.out',
        delay: index * 0.05, // escalonado bonito
        scrollTrigger: {
          trigger: item,
          start: 'top 85%',
          toggleActions: 'play none none reverse',
          id: `item-animation-${index}`,
          // markers: true,
        }
      }
    );
  });

  // Reveal desde izquierda
  const revealLeft = document.querySelectorAll('.reveal');
  revealLeft.forEach((element, index) => {
    gsap.fromTo(
      element,
      {
        clipPath: 'inset(0 100% 0 0)',
        opacity: 0,
        y: 20
      },
      {
        clipPath: 'inset(0 0% 0 0)',
        opacity: 1,
        y: 0,
        duration: 1.2,
        ease: 'power4.out',
        delay: index * 0.05,
        scrollTrigger: {
          trigger: element,
          start: 'top 100%',
          toggleActions: 'play none none reverse',
          id: `reveal-animation-${index}`,
          // markers: true,
        }
      }
    );
  });

  // Reveal desde derecha
  const revealRight = document.querySelectorAll('.revealRight');
  revealRight.forEach((element, index) => {
    gsap.fromTo(
      element,
      {
        clipPath: 'inset(0 0 0 100%)',
        opacity: 0,
        y: 20
      },
      {
        clipPath: 'inset(0 0 0 0%)',
        opacity: 1,
        y: 0,
        duration: 1.2,
        ease: 'power4.out',
        delay: index * 0.05,
        scrollTrigger: {
          trigger: element,
          start: 'top 85%',
          toggleActions: 'play none none reverse',
          id: `reveal-animation-r-${index}`,
          // markers: true,
        }
      }
    );
  });
});

onUnmounted(() => {
  ScrollTrigger.getAll().forEach(trigger => trigger.kill());
});
</script>
<template>
  <header class="flex-c ai-c">
    <article class="cont-8">
      <div class="flex-c ai-c">
        <h1 class="shadow-1">Astrid</h1>
        <h2 class="shadow-" style="margin-bottom: 30px;">Mi Primera Comunión</h2>
        <Play></Play>
        <h2 class="shadow-2">Desliza hacia abajo</h2>
      </div>

    </article>
  </header>
  <main class=" ai-c">
    <!--PADRES-->
    <section class="flex-c ai-c gap-50 cont-8 mb-50">
      <img  src="./assets/icons/topd.svg" alt="hornament" width="90%">
      <p class="animatedItem">
        "Hoy te abro las puertas de mi mente, mi alma y mi corazón, para que vivas eternamente en mí. Protégeme, bendice mi camino y guíame siempre hacia ti, Señor Jesús."
      </p>
      <img src="./assets/icons/comu1.jpg" alt="hornament" width="60%">
      <p class="animatedItem">
        Un día tan especial merece ser compartido con quienes más quiero.<br>
        Me encantaría que me acompañaras a celebrar este momento lleno de alegría y fe..
      </p>
      <img src="./assets/icons/singled.svg" alt="hornament" height="50px">
      <p class="animatedItem">Con cariño y gratitud a quienes me acompaña en este día tan especial, mis Madrinas:</p>
      <h2>
        <span class="reveal color-rosa">
        Yareth Domínguez
      </span>
      <br></br>
      <span class="reveal color-rosa">
        &
      </span>
      <br></br>
      <span class="reveal color-rosa">
        Karina Leon Cázales
      </span>
      </h2>
      <p class="animatedItem"> Con todo mi amor y agradecimiento a la persona que me guía y me brinda su apoyo incondicional, mi Mamá:</p>
      <h2>
        <span class=" reveal color-rosa">Daniella Domínguez</span>
      </h2>
      <img src="./assets/icons/bottomd.svg" alt="hornament" width="80%">
    </section>
    <!--TIMER-->
    <section id="time" class="flex-c jc-c" style="padding-left: 10%; padding-right: 10%;">
      <h2 class="reveal color-rosa">Faltan:</h2>
      <timer class="reveal color-rosa"></timer>
    </section>
    <!--DATE-->
    <section class="flex-c ai-c pv-50 gap-50 cont-8">
      <img src="./assets/icons/topd.svg" alt="hornament" width="90%">
      <article class="reveal flex gap-10 ai-c color-rosa">
        <h2>SÁBADO</h2>
        <h1>04</h1>
        <h2>OCTUBRE</h2>
      </article>
      <img src="./assets/icons/bottomd.svg" alt="hornament" width="80%">
    </section>
    <!--RECEPCION-->
    <section class="flex-c ai-c gap-50 mb-50">
      <article class="flex-c ai-c gap-30 cont-8">
        <h2 class="animatedItem color-rosa">Jardin Avellano</h2>
        <h3 class="animatedItem">Horario: 2:00 p.m.</h3>
        <p class="animatedItem">Rinconada de Los Gallos, Villas las Américas, 72810 San Andrés Cholula, Pue.</p>
      </article>
      <div id="church" class="flex-c ai-c jc-c">
        <a class="link-btn animatedItem" href="https://maps.app.goo.gl/9VdhwpH2j5y7PnUP7" target="_blank">Ver Ubicación</a>
      </div>
    </section>

    
    <!--REGALO-->
    <section class="flex-c ai-c gap-50 pv-50 cont-8 ">

      <img src="./assets/icons/topd.svg" alt="hornament" width="90%">
      <h1 class="reveal color-rosa">Opciones de Regalo</h1>
      <p class="animatedItem">Lo que más valoro es tu compañía en este día tan especial; sin embargo, si deseas tener un detalle conmigo, te sugiero:</p>
      <div class="animatedItem">
        <h2 class="reval color-rosa">Lluvia de sobres</h2>
        <img src="./assets/icons/gift.svg" alt="hornament" width="70%">
      </div>

      <img src="./assets/icons/bottomd.svg" alt="hornament" width="80%">
    </section>
    <!--ASISTENCIA-->
    <section class="flex-c ai-c gap-50 pv-50 cont-8 ">
      <img src="./assets/icons/topd.svg" alt="hornament" width="90%">
      <h1 class="reveal color-rosa">Asistencia</h1>
      <p class="animatedItem">Te agradecemos confirmar tu asistencia. Esperamos contar contigo</p>
      <div>
        <a
          class="animatedItem link-btn-2"
          href="https://wa.me/522229291370?text=¡Hola!%20Confirmo%20mi%20asistencia%20a%20la%20fiesta%20🥳"
          target="_blank"
        >
        Confirmar asistencia
        </a>
      </div>
      <img src="./assets/icons/singled.svg" alt="hornament" width="50px">
      <p class="animatedItem">"Con gratitud a Dios y a ustedes por acompañarme en este día tan especial:"</p>
      <div>
        <h1 class="reveal color-rosa" style="font-size: 100px; line-height: 85px;">Astrid</h1>
      </div>
    </section>
  </main>
  <footer>
    <article class="flex-c ai-c jc-c">
      <h1 class="reveal color-rosa" style="font-size: 20px; line-height: 350px;">
        Derechos Reservados Ulises Flores Grande
      </h1>
    </article>
  </footer>
</template>
