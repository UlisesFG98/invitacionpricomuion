<script setup>
import Timer from './components/Timer.vue';
import Play from './components/Play.vue';

import { ref, computed, onMounted, onUnmounted } from 'vue';
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

//const animatedElement= ref(null);

onMounted(() => {
  const items = document.querySelectorAll('.animatedItem');

  items.forEach((item, index) => {
    gsap.fromTo(
      item, {
      //INITIAL STATE
      opacity: 0,
      y: 50
    },
      {//FINAL STATE
        opacity: 1,
        y: 0,
        duration: .8,
        ease: 'power4.out',

        scrollTrigger: {
          trigger: item,
          start: 'top 90%',
          end: 'bottom 80%',
          scrub: true,
          //markers:true,
          id: `item-animation-${index}`
        }
      }
    );
  });
});
onMounted(() => {
  const revealElement = document.querySelectorAll('.reveal');
  revealElement.forEach((element, index) => {
    gsap.fromTo(
      element, {
      //INITIAL STATE
      clipPath: 'inset(0 100% 0 0)',
      opacity: 0,
      y: 20
    },
      {//FINAL STATE
        clipPath: 'inset(0 0% 0 0)',
        opacity: 1,
        y: 0,
        duration: 2,
        ease: 'power4.out',

        scrollTrigger: {
          trigger: element,
          start: 'top 80%',
          end: 'bottom 60%',
          scrub: true,
          //markers:true,
          id: `reveal-animation-${index}`
        }

      }

    );
  });
});
onMounted(() => {
  const revealElement = document.querySelectorAll('.revealRight');
  revealElement.forEach((element, index) => {
    gsap.fromTo(
      element, {
      //INITIAL STATE
      clipPath: 'inset(0 0 0 100%)',
      opacity: 0,
      y: 20
    },
      {//FINAL STATE
        clipPath: 'inset(0 0 0 0%)',
        opacity: 1,
        y: 0,
        duration: 2,
        ease: 'power4.out',

        scrollTrigger: {
          trigger: element,
          start: 'top 80%',
          end: 'bottom 60%',
          scrub: true,
          //markers:true,
          id: `reveal-animation-r-${index}`
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
        <h1 class="shadow-1">Camila</h1>
        <h2 class="shadow-2" style="margin-bottom: 30px;">MIS XV AÑOS</h2>
        <Play></Play>
        <h2 class="shadow-2">Desliza hacia abajo</h2>
      </div>

    </article>
  </header>
  <main class=" ai-c">
    <!--PADRES-->
    <section class="flex-c ai-c gap-50 cont-8 mb-50">
      <img src="./assets/icons/top.svg" alt="hornament" width="90%">
      <p class="animatedItem">Hay momentos que atesoramos por siempre, y para que este sea uno de ellos, me encantaría
        compartirlo contigo.
      </p>
      <img src="./assets/icons/single.svg" alt="hornament" height="50px">
      <p class="animatedItem">Gracias al amor inmenso y al apoyo incondicional de mis padres:</p>
      <h2>
        <span class="reveal color-dark-mint">Sara Sonia Grande Rodríguez</span><br>
        <span class="reveal">&</span><br>
        <span class=" reveal color-dark-mint">Francisco Flores Tapia</span>
      </h2>
      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>
    <!--TIMER-->
    <section id="time" class="flex-c jc-c" style="padding-left: 10%; padding-right: 10%;">
      <h2 class="reveal">Faltan:</h2>
      <timer class="reveal"></timer>
    </section>
    <!--DATE-->
    <section class="flex-c ai-c pv-50 gap-50 cont-8">
      <img src="./assets/icons/top.svg" alt="hornament" width="90%">
      <article class="reveal flex gap-10 ai-c color-dark-mint">
        <h2>SÁBADO</h2>
        <h1>23</h1>
        <h2>AGOSTO</h2>
      </article>
      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>
    <!--PARROQUIA-->
    <section class="flex-c ai-c gap-50 mb-50">
      <article class="flex-c ai-c gap-30 cont-8">
        <h2 class="animatedItem color-dark-mint">Parroquia de la Visitación de Santa Isabel Cholula</h2>
        <h3 class="animatedItem">12: 45 p.m.</h3>
        <p class="animatedItem">C. Zapata, Centro, 74350 Santa Isabel Cholula, Pue.</p>
      </article>
      <div id="church" class="flex-c ai-c jc-c">
        <a class="link-btn animatedItem" href="https://share.google/ETUQr0NVinfZOuy3t" target="_blank">Ver Ubicación</a>
      </div>
    </section>

    <!--RECEPCION-->
    <section class="flex-c ai-c gap-50 cont-8">

      <img src="./assets/icons/single.svg" alt="hornament" height="50px">

      <article class="flex-c ai-c gap-30 cont-8">
        <h2 class="animatedItem color-dark-mint">Hogar de la Familia Flores Grande</h2>
        <h3 class="animatedItem">Después de la ceremonia religiosa</h3>
        <p class="animatedItem">Calle Hidalgo número 25</p>
      </article>
      <a class="link-btn-2 animatedItem" href="https://share.google/xW7aTupCCfDIlpYPm" target="_blank">Ver Ubicación</a>

      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>

    <!--VESTIMENTA-->
    <section class="flex-c ai-c gap-50 pv-50 cont-8 ">
      <h1 class="reveal color-dark-mint">Código de vestimenta</h1>
      <article class="animatedItem flex gap-50 jc-sb cont-8">
        <div class="flex-c gap-20">
          <img src="./assets/icons/woman.svg" alt="woman" height="130px">
          <h3>Mujeres</h3>
        </div>
        <div class="flex-c gap-20">
          <img src="./assets/icons/man.svg" alt="men" height="130px">
          <h3>Hombres</h3>
        </div>
      </article>
      <h2 class="animatedItem">Evitar usar ropa en tonalidades verdes.</h2>
      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>
    <!--ITINERARIO-->
    <section id="ITINERARIO" class="flex-c ai-c">
      <article class="flex-c ai-c gap-50 pv-50 cont-8">
        <h1 class="animatedItem">Itinerario</h1>
        <!----------->
        <div class="revealRight flex ai-c">
          <div class="circle">
            <img src="./assets/icons/church.svg" height="60%" alt="Ceremonia">
          </div>
          <div>
            <h2 class="ph-20">Ceremonia</h2>
            <hr class="strg-ln">
            <p>12:45 p.m.</p>
          </div>
        </div>
        <!----------->
        <div class="reveal flex ai-c">
          <div>
            <h2 class="ph-20">Recepción</h2>
            <hr class="strg-ln">
            <p>03:00 p.m.</p>
          </div>
          <div class="circle">
            <img src="./assets/icons/ballons.svg" height="60%" alt="Recepción">
          </div>
        </div>
        <!----------->
        <div class="revealRight flex ai-c">
          <div class="circle">
            <img src="./assets/icons/dance.svg" height="60%" alt="cake">
          </div>
          <div>
            <h2 class="ph-20">Vals</h2>
            <hr class="strg-ln">
            <p>08:00 p.m.</p>
          </div>
        </div>
        <!----------->
        <div class="reveal flex ai-c">

          <div>
            <h2 class="ph-20">Brindis</h2>
            <hr class="strg-ln">
            <p>08:30 p.m.</p>
          </div>
          <div class="circle">
            <img src="./assets/icons/cheers.svg" height="60%" alt="cake">
          </div>
        </div>
        <!----------->
        <div class="revealRight flex ai-c">
          <div class="circle">
            <img src="./assets/icons/cake.svg" height="60%" alt="cake">
          </div>
          <div>
            <h2 class="ph-20">Pastel</h2>
            <hr class="strg-ln">
            <p>09:00 p.m.</p>
          </div>
        </div>

        <h3 class="animatedItem">Hasta que el cuerpo aguante o hasta que se terminen los buenos momentos</h3>


      </article>

    </section>
    <!--REGALO-->
    <section class="flex-c ai-c gap-50 pv-50 cont-8 ">

      <img src="./assets/icons/top.svg" alt="hornament" width="90%">
      <h1 class="reveal color-dark-mint">Opciones de Regalo</h1>
      <p class="animatedItem">Lo más importante es su compañía en este día especial para mí, sin embargo, si deseas
        darme un regalo, puedo sugerir:</p>
      <div class="animatedItem">
        <h2 class="color-dark-mint">Lluvia de sobres</h2>
        <img src="./assets/icons/gift.svg" alt="hornament" width="70%">
      </div>

      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>
    <!--REGALO-->
    <section id="photos" class="flex-c ai-c" style="width: 100%; justify-content: end;">
      <article class="flex-c ai-c pv-50 gap-10 cont-8">
        <h2 class="reveal color-white">¡Hagamos una fiesta épica!</h2>
        <p class="animatedItem color-white">Comparte tus fotos y recuerdos en este día tan especial</p>
        <a class="animatedItem link-btn-2" href="https://www.instagram.com/cams___fg" target="_blank"
          style="gap: 0; margin-bottom: 10px;">
          <img src="./assets/icons/insta.svg" alt="" width="50px">
          <p class="color-white" style="background: none;">#XVCAMS</p>
        </a>
      </article>
    </section>
    <!--ASISTENCIA-->
    <section class="flex-c ai-c gap-50 pv-50 cont-8 ">
      <img src="./assets/icons/top.svg" alt="hornament" width="90%">
      <h1 class="reveal color-dark-mint">Asistencia</h1>
      <p class="animatedItem">Te agradecemos confirmar tu asistencia. Esperamos contar contigo</p>
      <div>
        <a
          class="animatedItem link-btn-2"
          href="https://wa.me/522229005731?text=¡Hola!%20Confirmo%20mi%20asistencia%20a%20la%20fiesta%20🥳"
          target="_blank"
        >
        Confirmar asistencia
        </a>
      </div>
      <img src="./assets/icons/single.svg" alt="hornament" width="50px">
      <p class="animatedItem">Gracias por formar parte de uno de los mejores días de mi vida con cariño:</p>
      <div>
        <img class="animatedItem" src="/img/crown.png" alt="hornament" width="90%">
        <h1 class="reveal color-dark-mint" style="font-size: 100px; line-height: 85px;">Camila</h1>
      </div>

      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
      <div>
        <p class="animatedItem">Derechos Reservados Ulises Flores Grande</p>
      </div>
    </section>
  </main>
</template>
