<section id="sticky-name">
    <img class="name-img" src="/images/name.png" alt="Naam" width="430" height="400" loading="lazy" />
</section>
  
  <section class="srollabel">
    <p style="height:200vh">Scroll om het effect te zien…</p>
  </section>
  
  <div class="wrapper">
    <section class="character">
      <img class="character-img" src="/images/character.png" alt="Character" width="150" height="300" loading="lazy" />
    </section>
  
    <section class="content">
      <h2>WHO AM I?</h2>
      <p>
        Hi, I’m Nayome Kaia, 21 years old. I’m a Front-End Developer & Designer
        with a passion for mixing art, creativity, and technology.
      </p>
      <p>
        I love experimenting with CSS, animation, and interactive design to make
        websites feel alive and fun. For me, coding isn’t just technical—it’s a
        way to create experiences that people can feel.
      </p>
    </section>
</div>
  
  <style>
    @keyframes header-shrink {
      from {
        height: 100vh;
        background-position: 50% 0%;
      }
      to {
        height: 12vh;
        background-position: 50% 100%;
      }
    }
  
    @keyframes name-scale {
      from {
        transform: translate(-50%, -50%) scale(1);
      }
      to {
        transform: translate(-50%, -45%) scale(0.3);
      }
    }
  
    @keyframes character-fade-move {
      from {
        opacity: 1;
        transform: translate(-50%, -50%) translateY(0) scale(1);
      }
      to {
        opacity: 1;
        transform: translate(-50%, -70%) scale(0.9);
      }
    }
  
    #sticky-name {
      position: fixed;
      inset: 0 0 auto 0;
    
      /* scroll animatie van header */
      animation: header-shrink linear forwards;
      animation-timeline: scroll();
      animation-range: 0vh;
    }
  
    .name-img {
      position: absolute;
      top: 50%;
      left: 50%;
      height: auto;
      transform: translate(-50%, -50%) scale(1);
     
      /* scrol animatie van de naam */
      animation: name-scale linear forwards;
      animation-timeline: scroll();
      animation-range: 0vh;
    }
  
    .character {
      position: fixed;
      inset: 0;
     
    }
  
    .character-img {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
   
      /* floating animatie op mobiel dezd moet ik nog laten werken */
      animation: floating 4s ease-in-out infinite,
      character-fade-move linear forwards;
      animation-timeline: scroll();
    }
  
    @keyframes floating {
      0% {
        transform: translate(-50%, -50%) translateY(0) scale(1);
      }
      50% {
        transform: translate(-50%, -50%) translateY(-15px) scale(1.02);
      }
      100% {
        transform: translate(-50%, -50%) translateY(0) scale(1);
      }
    }
  
    .content {
      max-width: 600px;
      padding: 2rem;
      line-height: 1.6;
    }
