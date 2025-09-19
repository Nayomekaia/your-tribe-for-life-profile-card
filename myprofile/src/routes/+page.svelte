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
  inset: 0;
  pointer-events: none;
}

.character-img {
  position: absolute;
  top: 50%;
  left: 50%;
 
  transform: translate(-50%, -50%);

  /* 1) eerst de time-based float, daarna de scroll-anim */
  animation: 
    floating 4s ease-in-out infinite,
    character-fade-move linear forwards;

  /* 2) geef ze aparte timelines: time (auto) + scroll */
  animation-timeline: auto, scroll();

  /* 3) optioneel: range alleen voor de scroll-anim */
  animation-range: initial, 0vh 70vh;

  pointer-events: none;
}

@keyframes floating {
  0%   { translate: 0 0; }
  50%  { translate: 0 -15px; }
  100% { translate: 0 0; }
}

@keyframes character-fade-move {
  from { opacity: 1; transform: translate(-50%, -50%) scale(1); }
  to   { opacity: 0; transform: translate(-50%, -70%) scale(0.9); }
}


  .content {
  position: relative;
  z-index: 30;
  max-width: 600px;
  margin: 0 auto;              
  padding: 2rem 1.5rem;
  text-align: center;          
  line-height: 1.3;            
  display: flex;               
  flex-direction: column;
  justify-content: center;
  min-height: 100vh;       
  }    

.content h2 {
  margin: 0.5rem 0;           
}

.content p {
  margin: 0.3rem 0;           
}

.skills {
  justify-content: center;    
}

.skills li {
  margin: 0.2rem 0;           
}

  @media (min-width: 700px) {
    .wrapper {
      display: grid;
      grid-template-columns: minmax(380px, 600px) 1fr;
      align-items: center;
      min-height: 100vh;
      gap: 2rem;
      max-width: 1100px;
      margin: 0 auto;
      position: relative;
    }
    .content {
      margin: 0;
      align-self: center;
      justify-self: start;
      max-width: 50ch;
      font-size: large;
    }
    .character-img {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 250px;
  height: auto;
  pointer-events: none;
  transform: translate(-50%, -50%) scale(1);

  /* 1) beide animaties in één declaration */
  animation: 
    floating 4s ease-in-out infinite,
    to-right-desktop linear forwards;

  /* 2) aparte timelines per animatie: tijd + scroll */
  animation-timeline: auto, scroll();

  /* 3) optioneel: alleen range voor de scroll-anim */
  animation-range: initial, 0vh 70vh;
}

}
</style>
