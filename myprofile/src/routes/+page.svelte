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
    .character {
      position: fixed;
      inset: 0;
     
    }
  
    .character-img {
      position: absolute;
      top: 50%;
      left: 50%;
    .content {
      max-width: 600px;
      padding: 2rem;
      line-height: 1.6;
    }
