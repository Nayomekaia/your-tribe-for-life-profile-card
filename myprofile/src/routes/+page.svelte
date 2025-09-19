<section id="sticky-name">
  <img class="name-img" src="/images/name.png" alt="Naam" width="430" height="400" loading="lazy" />
</section>

<section class="srollabel">
  <p style="height:200vh">Scroll om meer informatie te krijgen</p>
</section>

<div class="wrapper">
  <section class="character">
    <img class="character-img" src="/images/character.png" alt="Character" width="150" height="300" loading="lazy" />
  </section>

  <section class="content">
    <p>I'm</p>
    <h2>Nayome Kaia</h2>

    <article>
    <p>I'm 21 years old</p>
    <p>Front end developer and designer</p>
    <p>Blending art with technology</p>
    <p>Passionate about movement & animation</p>
  </article>

    <ul class="skills">
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
      <li>Node.js</li>
      <li>Liquid</li>
      <li>JSON</li>
      <li>Figma</li>
      <li>SvelteKit</li>
    </ul>

    <section class="social-icons">
      <a href="https://github.com/Nayomekaia">
        <img src="/images/github.png" alt="GitHub" />
      </a>
      <a href="https://www.linkedin.com/in/nayome-doelwijt-2370172a5/">
        <img src="/images/linkedin.png" alt="LinkedIn" />
      </a>
    </section>
    
  </section>
</div>

<style>
.srollabel p {
  font-size: 1rem;
  max-width: 40ch;        
  margin: 20px;
}

article {
  margin: 1rem 0;           
  padding: 1rem;            
}

article p {
  margin: 0.2rem 0;           
  font-size: 1rem;
  text-align: left;
}
  
  .social-icons {
  display: flex;
  justify-content: center;   
  gap: 1rem;                 
  margin-top: 1.5rem;
}

.social-icons a img {
  width: 32px;   
  height: 32px;
  object-fit: contain;
  transition: transform 0.2s ease, filter 0.2s ease;
}


.social-icons a img:hover {
  transform: translateY(-4px) scale(1.1);
  filter: drop-shadow(2px 2px 0  green);
}

  .skills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.6rem;
    margin: 1rem 0;
    padding: 0;
    list-style: none;
  }
  
  .skills li {
  display: inline-block;
  font-size: 0.9rem;
  background: white;
  color: black;
  border: 3px solid black;
  border-radius: 8px;
  padding: 0.4rem 0.8rem;
  cursor: default;
  box-shadow: 3px 3px 0 black;
  transition: transform 0.15s ease, box-shadow 0.15s ease;
}

.skills li:hover {
  animation: jump 0.4s ease;
}

@keyframes jump {
  0%   { transform: translateY(0); }
  30%  { transform: translateY(-20px); }  
  50%  { transform: translateY(0); }
  70%  { transform: translateY(10px); } 
  100% { transform: translateY(0); }
}


  /* === SCROLL ANIMS (ongewijzigd) === */
  @keyframes header-shrink {
    from { height: 100vh; background-position: 50% 0%; }
    to   { height: 12vh;  background-position: 50% 100%; }
  }
  @keyframes name-scale {
    from { transform: translate(-50%, -50%) scale(1); }
    to   { transform: translate(-50%, -45%) scale(0.3); }
  }
  @keyframes character-fade-move {
    from { opacity: 1; transform: translate(-50%, -50%) translateY(0) scale(1); }
    to   { opacity: 0; transform: translate(-50%, -70%) scale(0.9); }
  }

  #sticky-name {
    position: fixed;
    inset: 0 0 auto 0;
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
    animation: name-scale linear forwards;
    animation-timeline: scroll();
    animation-range: 0vh;
  }

  .character {
  position: fixed;
  inset: 0;
  z-index: 12;
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
