<script setup>
import Timer from './components/Timer.vue';
</script>

<template>
  <header class="flex-c ai-c">
    <div class="cont-8">
      <h1 class="shadow-1">Camila</h1>
      <h2 class="shadow-2  mb-40">MIS XV AÑOS</h2>
      <img src="./assets/icons/play.svg" width="60px" alt="">
      <h2 class="fs-40 mb-50">play</h2>
      <h2 class="shadow-2">Desliza para ver invitación.</h2>
    </div>
  </header>
  <main class="ai-c">
    <section class="flex-c ai-c gap-50 cont-8 mb-50">
      <img src="./assets/icons/top.svg" alt="hornament" width="90%">
      <p>Hay momentos que atesoramos por siempre, y para que este sea uno de ellos, me encantaría compartirlo contigo.
      </p>
      <img src="./assets/icons/single.svg" alt="hornament" height="50px">
      <p>Gracias al amor inmenso y al apoyo incondicional de mis padres:</p>
      <h2>
        <span class="color-dark-mint">Sara Sonia Grande Rodríguez</span><br>
        <span>&</span><br>
        <span class="color-dark-mint">Francisco Flores Tapia</span>
      </h2>
      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>
    <section id="time" class="flex-c jc-c" style="padding-left: 10%; padding-right: 10%;">
      <h2>Faltan:</h2>
      <timer></timer>
    </section>
    <section class="flex-c ai-c pv-50 gap-50 cont-8">
      <img src="./assets/icons/top.svg" alt="hornament" width="90%">
      <article class="flex gap-10 ai-c color-dark-mint">

        <h2>SÁBADO</h2>
        <h1>23</h1>
        <h2>AGOSTO</h2>
      </article>
      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>
    <!--PARROQUIA-->
    <section class="flex-c ai-c gap-50 mb-50">
      <article class="flex-c ai-c gap-30 cont-8">
        <h2 class="color-dark-mint">Parroquia de la Visitación de Santa Isabel Cholula</h2>
        <h3>12: 45 p.m.</h3>
        <p>C. Zapata, Centro, 74350 Santa Isabel Cholula, Pue.</p>
      </article>
      <div id="church" class="flex-c ai-c jc-c">
        <a class="link-btn" href="https://share.google/ETUQr0NVinfZOuy3t" target="_blank">Ver Ubicación</a>
      </div> 
    </section>
    
    <!--RECEPCION-->
    <section class="flex-c ai-c gap-50 cont-8">
      
      <img src="./assets/icons/single.svg" alt="hornament" height="50px">
      
      <article class="flex-c ai-c gap-30 cont-8">
        <h2 class="color-dark-mint">Residencia de la Familia Flores Grande</h2>
        <h3>Después de la ceremonia religiosa</h3>
        <p>Calle Hidalgo número 25</p>
      </article>
      <a class="link-btn-2" href="https://share.google/xW7aTupCCfDIlpYPm" target="_blank">Ver Ubicación</a>
      
      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>
    
    <!--VESTIMENTA-->
    <section class="flex-c ai-c gap-50 pv-50 cont-8 ">
      <h1 class="color-dark-mint">Código de vestimenta</h1>
      <article class="flex gap-50 jc-sb cont-8">
        <div class="flex-c gap-20">
          <h3>Mujeres</h3>
          <p class="fs-20">Vestido o mono cualquier largo</p>
          <p class="fs-20">Bolso de mano</p>  
          <p class="fs-20">Tacones o plataformas</p>  
        </div>
        <div class="flex-c gap-20">
          <h3>Hombres</h3>
          <p class="fs-20">Traje o blazer</p>
          <p class="fs-20">Camisa de vestir</p>  
          <p class="fs-20">Corbata opcional</p>
          <p class="fs-20">Zapato formal o mocasines</p>
        </div>
      </article>
      <H2>Evitar usar ropa en tonalidades verdes.</H2>
      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>
    <!--ITINERARIO-->
    <section id="ITINERARIO" class="flex-c ai-c">
      <article class="flex-c ai-c gap-50 pv-50 cont-8">
        <h1 class="">Itinerario</h1>
        <div>
          <h2>Ceremonia</h2>
          <hr>
          <p>01:00 p.m.</p>
        </div>
        
        <div>
          <h2>Recepción</h2>
          <hr>
          <p>03:00 p.m.</p>
        </div>
        <div>
          <h2>Vals</h2>
          <hr>
          <p>08:00 p.m.</p>
        </div>
        <div>
          <h2>Brindis </h2>
          <hr>
          <p>08:30 p.m.</p>
        </div>
        
        <div>
          <h2>Pastel</h2>
          <hr>
          <p>09:00 p.m.</p>
        </div>

        <h3>Hasta que el cuerpo aguante o hasta que se terminen los buenos momentos</h3>
        
        
      </article>

    </section>
    <!--REGALO-->
    <section class="flex-c ai-c gap-50 pv-50 cont-8 ">
      
      <img src="./assets/icons/top.svg" alt="hornament" width="90%">
      <h1 class="color-dark-mint">Opciones de Regalo</h1>
      <p>Lo más importante es su compañía en este día especial para mí, sin embargo, si deseas darme un regalo, puedo sugerir:</p>
      <div>
        <h2 class="color-dark-mint">Lluvia de sobres</h2>
        <img src="./assets/icons/gift.svg" alt="hornament" width="70%">
      </div>
      
      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>
    <!--REGALO-->
    <section id="photos" class="flex-c ai-c" style="width: 100%; justify-content: end;">
      <article class="flex-c ai-c pv-50 gap-10 cont-8">
        <h2 class="color-white">¡Hagamos una fiesta épica!</h2>
        <p class="color-white">Comparte tus fotos y recuerdos en este día tan especial</p>
        <a class="link-btn-2" href="https://www.instagram.com/cams___fg" target="_blank" style="gap: 0; margin-bottom: 10px;">
          <img src="./assets/icons/insta.svg" alt="" width="50px">
          <p class="color-white" style="background: none;">#XVCAMS</p>
        </a>
      </article>
    </section>
    <!--ASISTENCIA-->
    <section class="flex-c ai-c gap-50 pv-50 cont-8 ">
      <img src="./assets/icons/top.svg" alt="hornament" width="90%">
      <h1 class="color-dark-mint">Asistencia</h1>
      <p>Te agradecemos confirmar tu asistencia. Esperamos contar contigo</p>
      <div>
        <a class="link-btn-2" href="https://wa.me/522229005731" target="_blank">Confirmar asistencia</a>  
      </div>
      <img src="./assets/icons/single.svg" alt="hornament" width="50px">
      <p>Gracias por formar parte de uno de los mejores días de mi vida con cariño:</p>
      <div>
        <img src="/img/crown.png" alt="hornament" width="90%">
      <h1 class="color-dark-mint" style="font-size: 100px; line-height: 85px;">Camila</h1>
      </div>
      
      <img src="./assets/icons/bottom.svg" alt="hornament" width="80%">
    </section>
  </main>
</template>
