---
layout: splash
permalink: /home-draft/
hidden: true
---
<style>


body {
  margin: 0;
  font-family: 'Inter', sans-serif;
  color: #222;
  scroll-behavior: smooth;
}

h1, h2, h3 {
  font-weight: 600;
}

a {
  color: #0055aa;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}




  .ws-hero {

  position: relative;
    background-attachment: fixed;
    background-position: center 60%;
    background-repeat: no-repeat;
    background-size: cover;
  
  }
  
  
  .ws-hero-banner {
   width: 100vw;
  margin-left: calc(50% - 50vw);
    height: 70vh;
    min-height: 70px;
    background-image: url("assets/images/eva-blue-banner.png");  
  }
  
    .ws-hero-sessions {
     width: 100vw;
    margin-left: calc(50% - 50vw);
    height: 20vh;
    min-height: 320px;
    background-image: url("https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/eva-blue-banner-no-title.png?raw=true");  
     display: flex;
    align-items: flex-end;
    justify-content: flex-start;
    overflow: hidden;
      margin-top: 0.5rem;
  }

  .ws-hero__overlay {
    position: absolute;
    inset: 0;
  }


  .ws-hero__grid {
    position: absolute;
    inset: 0;
    background-size: 48px 48px;
    pointer-events: none;
  }
  
  .ws-talks {
  background: 
    linear-gradient(rgba(0,0,0,0.35), rgba(0,0,0,0.35)), /* contrast layer */
linear-gradient(
  135deg,
  rgba(0, 90, 50, 0.95) 0%,   
  rgba(0, 200, 120, 0.75) 60%, 
  rgba(0, 90, 50, 0.55) 100%  
);
}

  .ws-talks-grid {
   background-image:
   linear-gradient(rgba(255, 220, 120, 0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 220, 120, 0.06) 1px, transparent 1px);
}



  .ws-workshops {
    background: linear-gradient(
      135deg,
      rgba(0, 42, 65, 0.92) 0%,
      rgba(41, 117, 193, 0.70) 60%,
      rgba(0, 42, 65, 0.50) 100%
    );
  }
      
 .ws-workshops-grid {
    background-image:
      linear-gradient(rgba(255,255,255,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.04) 1px, transparent 1px);
}


  .ws-tutorials {
  background: 
    linear-gradient(rgba(0,0,0,0.35), rgba(0,0,0,0.35)),
    linear-gradient(
      135deg,
      rgba(120, 90, 0, 0.95) 0%,
      rgba(255, 200, 0, 0.75) 60%,
      rgba(120, 90, 0, 0.55) 100%
    );
  }
      
 .ws-tutorials-grid {
 background-image:
   linear-gradient(rgba(255, 220, 120, 0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 220, 120, 0.06) 1px, transparent 1px);
}


  .ws-keynotes {
background: 
linear-gradient(
  135deg,
  rgba(50, 15, 55, 0.95) 0%,   
  rgba(104, 36, 109, 0.80) 55%, 
  rgba(104, 36, 109, 0.55) 100%
);
  }
      
 .ws-keynotes-grid {
   background-image:
   linear-gradient(rgba(255, 220, 120, 0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 220, 120, 0.06) 1px, transparent 1px);
}





  .ws-hero__content {
    position: relative;
    z-index: 2;
    padding: 0 3rem 3rem;
    max-width: 860px;
    text-align: left;
  }

  .ws-hero__eyebrow {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.65);
    margin-bottom: 0.75rem;
  }

  .ws-hero__eyebrow::before {
    content: '';
    display: block;
    width: 28px;
    height: 2px;
  background: #ffffff;
    border-radius: 2px;
  }

  .ws-hero h1 {
    
    font-size: clamp(2.4rem, 5vw, 4rem);
    font-weight: 400;
    color: #ffffff;
    margin: 0 0 0.5rem;
    line-height: 1.08;
    letter-spacing: -0.02em;
  }

  .ws-hero h1 em {
    font-style: italic;
    color: #7ec8ff;
  }

.ws-hero-cta {
  margin-top: 1rem;

  display: inline-flex;
  align-items: center;
  justify-content: flex-start;
  gap: 0.4rem;

  font-size: 0.85rem;
  font-weight: 600;
  letter-spacing: 0.08em;

  color: #ffffff !important;
  text-decoration: none;

  padding: 0.5rem 1rem;
  border-radius: 999px;

  background: rgba(255,255,255,0.12);
  backdrop-filter: blur(6px);

  transition: all 0.3s ease;
}


.ws-hero-cta:hover {
  background: rgba(255,255,255,0.22);
  transform: translateY(-2px);
}

/* Arrow animation */
.ws-hero-cta span {
  transition: transform 0.3s ease;
}

.ws-hero-cta:hover span {
  transform: translateX(4px);
}
  
  

  
  
  
.herovid {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 3rem 1rem;
  width: 100%;
}

.hero-inner {
  position: relative;
  max-width: 960px;
  width: 100%;
  margin: 0 auto;
  border-radius: 14px;
  overflow: hidden;
  box-shadow: 0 8px 24px rgba(0,0,0,0.25);
}

.hero-video {
  position: relative;
  width: 100%;
  aspect-ratio: 16 / 9;
  overflow: hidden;
}

#yt-player {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.hero-inner::before {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0,0,0,0.35);
  z-index: 1;
}

.hero-content {
  position: absolute;
  inset: 0;
  z-index: 2;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  text-align: center;
  color: white;
  padding: 1.5rem;
}

.hero-content h1 {
  margin-bottom: 0.5rem;
}

.hero-content p {
  max-width: 600px;
  margin-bottom: 1rem;
}



.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;

  padding: 1rem 2.4rem;
  border-radius: 999px;

  font-weight: 700;
  font-size: 1rem;
  letter-spacing: 0.3px;

  text-decoration: none;
  cursor: pointer;

  transition: all 0.25s ease;
}

.btn-purple {
  background:  #002A41;
  color: #ffffff !important;
  box-shadow: 0 8px 20px rgba(0, 42, 65, 0.25);
  margin-bottom: 2rem;
}

.btn-purple:hover {
  transform: translateY(-4px);
  box-shadow: 0 14px 30px rgba(0, 42, 65, 0.35);
}

.btn-purple:active {
  transform: translateY(-1px);
}

.btn-purple:focus-visible {
  outline: 3px solid rgba(0, 61, 128, 0.5);
  outline-offset: 4px;
}



section {
  max-width: none;
  margin: 0;
  padding: 0;
  text-align: center;
}

section h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
  line-height: 1.2;
}

section p {
  font-size: 1.1rem;
  line-height: 1.7;
  color: #eeeeee;
}


  .hero-content p {
    font-size: 0.95rem;
    color: #ffffff !important;
  }
  
/* Custom text tag fix */
t {
  font-size: 1rem;
  line-height: 1.7;
  color: #002A41;
  display: block;
}



.dual-cards {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 2rem;
  max-width: 1300px;
  margin:0.5rem auto;
  padding: 0 2rem;
}

.call-for-submissions {
  background: #ffffff;
  border-top: 4px solid #002A41;
  box-shadow: 0 10px 25px rgba(0,0,0,0.06);
  padding: 2rem;
  border-radius: 20px;
  text-align: center;

  display: flex;
  flex-direction: column;
  justify-content: center;

  transition: all 0.3s ease;
}

.call-for-submissions:hover {
  transform: translateY(-6px);
  box-shadow: 0 25px 45px rgba(0,0,0,0.12);
}

.call-for-submissions h2 {
  font-size: 1.4rem;
  color: #002A41;
  margin-bottom: 0.5rem;
}

.deadline-box {
  font-size: 1rem;
  background: #f5f7fa;
  color: #002A41;
  padding: 0.9rem 1rem;
  border-radius: 14px;
  font-weight: 500;
  margin: 1rem 0 1.5rem 0;
}



.image-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1rem;
  margin-top: 2rem;
}

.image-grid img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  border-radius: 12px;
  transition: transform 0.4s ease, box-shadow 0.4s ease;
}

.image-grid img:hover {
  transform: scale(1.05);
  box-shadow: 0 12px 24px rgba(0,0,0,0.2);
}



.fade-in {
  opacity: 0;
  transform: translateY(40px);
  transition: all 0.8s ease-out;
}

.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}



.page__content,
.page__inner-wrap,
.wrapper,
.initial-content {
  max-width: 100% !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
}



.sponsors-strip {
  padding: 1rem 1.5rem 2rem;
  text-align: center;
}

.sponsors-container {
  max-width: 1100px;
}

.sponsors-strip h2 {
  font-size: 2.5rem;
  margin-bottom: 2rem;
  color: #68246D;
  font-weight: 600;
}

/* Grid */
.sponsors-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 2rem;
  align-items: center;
  margin-bottom: 2rem;
}

/* Logo card */
.sponsor-logo {
  background: #ffffff;
  border-radius: 12px;
  box-shadow: 0 6px 18px rgba(0,0,0,0.06);

  aspect-ratio: 1 / 1;         
  width: 100%;

  display: flex;               
  align-items: center;
  justify-content: center;

  padding: 1rem;

  transition: all 0.25s ease;
}

.sponsor-logo:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 28px rgba(0,0,0,0.12);
}

/* Logo image */
.sponsor-logo img {
  max-width: 80%;
  max-height: 80%;
  object-fit: contain;

  opacity: 0.85;
  transition: all 0.25s ease;
}




/* === Premium Infinite Carousel === */

.carousel-wrapper {
  position: relative;
  width: 100vw;
  margin-left: calc(50% - 50vw);
  overflow: hidden;
  padding: 1rem 0;

  /* Elegant fade edges */
  -webkit-mask-image: linear-gradient(
    to right,
    transparent 0%,
    black 10%,
    black 90%,
    transparent 100%
  );
  mask-image: linear-gradient(
    to right,
    transparent 0%,
    black 10%,
    black 90%,
    transparent 100%
  );
}

.carousel-track {
  display: flex;
  gap: 0.5rem;
  align-items: stretch;
}


.carousel-track {
  display: flex;
  gap: 0.5rem;
  align-items: stretch;
  will-change: transform;
  background: none;
}

.carousel-wrapper {
  overflow-x: auto;
}




/* ===== Cards ===== */
.session-card {
  width: 200px;
  flex: 0 0 300px;
  display: flex;

  background: none;
  padding: 0;
  border: none;
}


.about-card {
  background: #ffffff;
  border-radius: 18px;
  padding: 1.3rem 1.4rem;
  box-shadow: 0 10px 26px rgba(0,0,0,0.06);

  display: flex;
  flex-direction: column;
  justify-content: space-between;

   height: 100%;

  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

/* Default fallback */
.session-card .about-card {
  border-top: 5px solid #cccccc;
}

/* Category colours */
.session-card.talk .about-card {
  border-top-color: #0077cc;   /* blue */
}

.session-card.tutorial .about-card {
  border-top-color: #00a86b;   /* green */
}

.session-card.keynote .about-card {
  border-top-color: #8e44ad;   /* purple */
}

.session-card.workshop .about-card {
  border-top-color: #e67e22;   /* orange */
}

.about-card:hover {
  transform: translateY(-6px) scale(1.02);
  box-shadow: 0 20px 45px rgba(0,0,0,0.12);
}


.card-title {
  font-size: 0.9rem;
  font-weight: 600;
  color: #002A41;

  line-height: 1.35;
  margin-bottom: 0.7rem;

  display: -webkit-box;
  -webkit-line-clamp: 3;   /* tighter for carousel */
  -webkit-box-orient: vertical;
  overflow: hidden;
  min-height: 5em;
}


.about-button {
  align-self: flex-start;

  font-size: 0.78rem;
  font-weight: 600;

  padding: 0.4rem 1rem;
  border-radius: 999px;

  background: #002A41;
  color: #fff !important;
  text-decoration: none;

  transition: all 0.2s ease;
}

.about-button:hover {
  background: #00a86b;
  transform: scale(1.05);
}


.card-details {
  margin: 0.5rem 0 0.8rem;
  display: flex;
  flex-direction: column;
  gap: 0.45rem;
    flex-grow: 1; 
}

.card-text {
  font-size: 0.6rem;
  color: #002A41;
  line-height: 1.45;
  text-align: left;
}

/* === REGISTER CTA (Premium) === */
.register-cta {
  position: relative;
  margin-top: 0!important;

    width: 100vw;
  margin-left: calc(50% - 50vw);

  background: linear-gradient(
    135deg,
    #053855 0%,
    #053855 25%,
    #003f63 50%,
    #005f73 100%
  );

  color: #ffffff;
  text-align: center;

  box-shadow: 0 20px 50px rgba(0, 42, 65, 0.25);

  overflow: hidden;
        margin-bottom: 0!important;
}

.register-cta-purple {
  background: linear-gradient(
    135deg,
    #2e0f3a 0%,   /* deep purple */
    #2e0f3a 25%,
    #4b1f5e 50%,  /* main purple */
    #6d2c7a 100%  /* lighter purple */
  );
      margin-bottom: 0!important;
}



/* subtle glow effect */
.register-cta::before {
  content: "";
  position: absolute;
  inset: 0;
  background: radial-gradient(
    circle at 20% 20%,
    rgba(255,255,255,0.08),
    transparent 60%
  );
}

.register-content {
  position: relative;
  z-index: 2;
  max-width: 700px;
  margin: 0 auto;
}

.register-cta h2 {
  font-size: 1.8rem;
  margin-bottom: 0.8rem;
  font-weight: 600;
}

.register-cta p {
  font-size: 1.05rem;
  line-height: 1.6;
  opacity: 0.9;
  margin-bottom: 1.2rem;
}

.register-meta {
  font-size: 0.95rem;
  opacity: 0.85;
  margin-bottom: 1.8rem;
}

/* stronger CTA button */
.btn-primary {
  background: #ffffff;
  color: #002A41 !important;
  font-weight: 700;

  padding: 1rem 2.6rem;
  margin-bottom: 3rem;
  border-radius: 999px;

  box-shadow: 0 10px 25px rgba(0,0,0,0.2);

  transition: all 0.25s ease;
  margin-bottom: 2rem;
}

.btn-primary:hover {
  transform: translateY(-3px) scale(1.03);
  box-shadow: 0 18px 35px rgba(0,0,0,0.3);
}

.full-bleed {
  width: 100vw;
  margin-left: calc(50% - 50vw);
    margin-right: calc(50% - 50vw);
}


@media (max-width: 900px) {

  .dual-cards {
    grid-template-columns: 1fr;
    padding: 0 1rem;
  }

  .hero-inner {
    border-radius: 10px;
  }

  .hero-content h1 {
    font-size: 1.5rem;
  }

  .hero-content p {
    font-size: 0.95rem;
    color: #ffffff !important;
  }
  


  .call-for-submissions {
    padding: 1.5rem;
  }

  .call-for-submissions .btn {
    width: 100%;
    padding: 1rem;
  }

  .image-grid {
    grid-template-columns: 1fr;
  }

  .image-grid img {
    height: auto;
  }

  section h2 {
    font-size: 1.5rem;
  }
  .about-grid {
    gap: 1.2rem;
  }

  .ws-hero__eyebrow {
    display: none;
  }
  
  .card-title {
    -webkit-line-clamp: 2;
  }



  .parallax-hero {
    background-attachment: scroll;
    height: 38vh;
  }
  
    .ws-hero {
    height: 30vh;
    min-height: 150px;
      align-items: center;
  justify-content: center;
  text-align: center;

  }

.ws-hero__content {
  padding: 0 1.5rem;
}

  .about-grid {
    gap: 1.5rem;
  }

  .card-title {
    font-size: 1.05rem;
    -webkit-line-clamp: 2; 
    min-height: 2.8em;
  }
  
   .ws-hero-banner {
   width: 100vw;
  margin-left: calc(50% - 50vw);
    height: 70vh;
    min-height: 70px;
    background-image: url("assets/images/eva-blue-banner.png");  
  }

}

@media (max-width: 900px) {
  
  .hero-content h1,
  .hero-content a:not([href*="youtu.be"]) {
    display: none;
  }


  .hero-content {
    justify-content: center;
  }
}

</style>


<section class="ws-hero ws-hero-banner full-bleed">
</section>





<section class="register-cta full-bleed fade-in">
  <div class="register-content">
    
    <div class="register-content">
      <h2>15th to 19th of June 2026</h2>
 
  <p>
    The <strong>Durham HPC Days</strong> bring together researchers, developers, and practitioners
    to explore the frontiers of high-performance computing, data analysis, and scientific innovation.
  </p>
      <div class="register-meta">
        📅 15–19 June 2026 &nbsp;&nbsp;•&nbsp;&nbsp; ⏳ Registration closes 20 April
      </div>

      <a href="https://pay.durham.ac.uk/event-durham/durham-hpc-days-2026" 
         class="btn btn-primary">
         Register now
      </a>
    </div>
    
</div>

  </section>
  






<section id="featured-sessions" class="fade-in">
  <h2>🎤 Featured Sessions</h2>

  <div class="carousel-wrapper">
    <div class="carousel-track">

{% assign talks = site.programme-days-2026 | sort: "start_time" %}

  
      
      
            {% for talk in talks %}
<a href="{{ talk.url }}" class="session-card {{ talk.category | downcase }}">
  <div class="about-card">

    <div class="card-title">{{ talk.title }}</div>

    <div class="card-details">

      <div class="card-row">
        <div class="card-text">
          📅 {{ talk.day }} · {{ talk.start_time }}–{{ talk.end_time }}
        </div>
      </div>

      {% if talk.room and talk.room != "TBC" %}
      <div class="card-row">
      <div class="card-text"> 📍 {{ talk.room }}</div>
      </div>
      {% endif %}

    </div>



  </div>
</a>
      {% endfor %}
      

    </div>
  </div>
</section>



<section id="programme" class="fade-in">
  <h2>🗓️ Explore the Programme</h2>
  <t style="max-width: 700px; margin: 0 auto 2rem;">
    Discover the full schedule of keynotes, technical sessions, and social events for the upcoming conference.
    Check the programme to plan your participation and make the most of your experience at Durham HPC Days.<br>
  </t><br>
  <a href="https://hpc-days.github.io/Durham-HPC-Days-2026/programme-hpcdays-2026/" class="btn btn-purple">Full programme coming up soon</a>
</section>


<section class="ws-hero ws-hero-sessions full-bleed">
  <div class="ws-keynotes ws-hero__overlay"></div>
  <div class="ws-keynotes-grid ws-hero__grid"></div>
  <div class="ws-hero__content">
    <h1>Keynotes</h1>
    <a href="/keynotes/" class="ws-hero-cta">
  Coming up soon <span>→</span>
</a>
  </div>
</section>
<section class="ws-hero ws-hero-sessions full-bleed">
  <div class="ws-talks ws-hero__overlay"></div>
  <div class="ws-talks-grid ws-hero__grid"></div>
  <div class="ws-hero__content">
    <h1>Talks</h1> <a href="/" class="ws-hero-cta">
  Coming up soon <span>→</span>
</a>
  </div>
</section>
<section class="ws-hero ws-hero-sessions full-bleed">
  <div class="ws-workshops ws-hero__overlay"></div>
  <div class="ws-workshops-grid ws-hero__grid"></div>
  <div class="ws-hero__content">
    <h1>Workshops</h1>
    <a href="/" class="ws-hero-cta">
  Coming up soon <span>→</span>
</a>
  </div>
</section>
<section class="ws-hero ws-hero-sessions full-bleed">
  <div class="ws-tutorials ws-hero__overlay"></div>
  <div class="ws-tutorials-grid ws-hero__grid"></div>
  <div class="ws-hero__content">
    <h1>Tutorials</h1>
    <a href="/tutorials/" class="ws-hero-cta">
  Explore tutorials <span>→</span>
</a>
  </div>
</section>






<div class="header-image"></div>

<section id="gallery" class="fade-in">
  <h2>📸 Gallery</h2>
  <div class="image-grid">
    <img src="assets/images/Sessions.jpg" alt="Sessions">
    <img src="assets/images/food-truck.jpg" alt="Food truck">
    <img src="assets/images/social.png" alt="social">
  </div>
</section>


<div class="herovid">
  <div class="hero-inner">
    <div class="hero-video">
      <div id="yt-player"></div>
    </div>
    <div class="hero-content">
    
      <h1>Durham HPC Days 2025 Video Recap</h1>
     
      <a href="https://durham.readthedocs.io/en/latest/hpcdays2025/index.html" class="btn btn-purple" target="_blank" rel="noopener">Visit last year's website</a>

      <a href="https://youtu.be/wPjtwACmaUg" class="btn btn-purple" target="_blank" rel="noopener">HPC Days 2025 Video</a>
    </div>
  </div>
</div>







<section class="register-cta  register-cta-purple full-bleed fade-in">
  <div class="register-content">
    
    <div class="register-content">
      <h2>Our Sponsors</h2>
 
  <p>
    If you are sponsoring and supporting HPC Days 2026, thank you very much! We would not be able to run the event without you!
  </p>
      
      
      
        <div class="sponsors-grid">

      <!-- Sponsor -->
      <a href="https://www.ddn.com" target="_blank" rel="noopener noreferrer">
      <div class="sponsor-logo">
        <img src="https://www.ddn.com/wp-content/uploads/2024/09/ddn-logo-dark-horizontal-rgb.jpg" alt="ddn">
      </div>
      </a>
      
      
      
      
      
      
<a href="https://eu.fsastech.com/eu/" target="_blank" rel="noopener noreferrer">
      <div class="sponsor-logo">
        <img src="https://media.licdn.com/dms/image/v2/D4D0BAQFz2Hw6LVRJlg/company-logo_200_200/B4DZWPBwyvHYAI-/0/1741861359139?e=2147483647&v=beta&t=sLukj4LFeyoCCButXJ0ICGVDUN3dEz_FDbeicBq3pNM" alt="Fsas Technologies">
      </div>
      </a>
      
      
 <a href="https://www.novatech.co.uk/" target="_blank" rel="noopener noreferrer">     
      <div class="sponsor-logo">
        <img src="https://media.licdn.com/dms/image/v2/D4E0BAQERb5GeBVwP7g/company-logo_200_200/company-logo_200_200/0/1688369383296/novatech_logo?e=2147483647&v=beta&t=DlfqUR3v9c8B9qftCRLVBJ4nlTTSYiolK0OFNqu5Fw8" alt="novatech">
      </div>
      </a>

<a href="https://ocf.co.uk/" target="_blank" rel="noopener noreferrer">
      <div class="sponsor-logo">
        <img src="https://ocf.co.uk/images/logoblue.png" alt="OCF">
      </div>
       </a>
      


<a href="https://vespertec.com" target="_blank" rel="noopener noreferrer">
<div class="sponsor-logo">
<svg xmlns="http://www.w3.org/2000/svg" xml:space="preserve" style="fill-rule:evenodd;clip-rule:evenodd;stroke-linejoin:round;stroke-miterlimit:2" width="236" height="60" viewBox="0 0 236 60"> <path d="M959.27.44 0 959.732 959.27 1919l959.29-959.268L959.27.44ZM495.458 588.934 959.27 125.101l463.88 463.876-463.88 463.813-463.812-463.856Zm990.012 62.384 308.37 308.414-834.57 834.588-834.566-834.588 308.413-308.414L959.27 1177.51l526.2-526.192Zm-208.32-447.023 33.44 34.138 67.02-66.327-33.79-34.507-66.67 66.696Zm-735.965-31.214 66.392 66.998 34.463-33.835-66.673-66.652-34.182 33.489Zm802.965 98.212 33.53 34.16 66.93-66.349-33.81-34.528-66.65 66.717Zm-869.941-31.214 66.348 67.02 34.442-33.857-66.652-66.651-34.138 33.488Zm936.961 98.191 33.44 34.224 67.02-66.37-33.81-34.506-66.65 66.652ZM407.189 307.099l66.37 66.955 34.485-33.835-66.674-66.674-34.181 33.554ZM1478.14 405.29l33.49 34.138 66.98-66.327-33.81-34.463-66.66 66.652ZM340.212 374.054l66.327 67.063 34.506-33.835-66.652-66.695-34.181 33.467Zm1204.978 98.212 33.42 34.181 67.02-66.304-33.86-34.507-66.58 66.63ZM273.17 441.117l66.327 66.977 34.528-33.879-66.652-66.651-34.203 33.553Zm1338.97 98.191 33.49 34.138 67-66.349-33.82-34.441-66.67 66.652ZM206.194 508.094l66.348 67.02 34.507-33.857-66.674-66.716-34.181 33.553Zm1472.926 98.19 33.51 34.182 67.02-66.327-33.86-34.528-66.67 66.673Zm-1539.946-31.17L205.5 642.09l34.55-33.878-66.695-66.651-34.181 33.553Zm-3.704 770.776 33.531 34.2 67.02-66.35-33.856-34.44-66.695 66.59Zm1545.47-33.06 66.39 67.02 34.5-33.81-66.69-66.65-34.2 33.44Zm-1478.45 100.1 33.531 34.18 66.955-66.31-33.835-34.57-66.651 66.7Zm1411.47-33.08 66.37 67 34.48-33.88-66.67-66.65-34.18 33.53ZM269.466 1479.91l33.51 34.2 67.064-66.35-33.879-34.51-66.695 66.66Zm1277.494-33.06 66.35 67.02 34.51-33.83-66.66-66.66-34.2 33.47ZM336.486 1546.93l33.554 34.2 66.976-66.33-33.856-34.57-66.674 66.7Zm1143.524-33.06 66.32 66.98 34.47-33.86-66.61-66.61-34.18 33.49ZM403.485 1613.92l33.531 34.19 66.977-66.33-33.813-34.51-66.695 66.65Zm1009.475-33.07 66.35 67.04 34.55-33.84-66.71-66.69-34.19 33.49Zm-942.455 100.09 33.488 34.21 66.977-66.35-33.814-34.55-66.651 66.69Zm875.485-33.05 66.33 66.98 34.46-33.86-66.61-66.63-34.18 33.51Zm-808.487 100.03 33.467 34.2 67.041-66.39-33.835-34.42-66.673 66.61Zm741.467-33.05 66.33 67.01 34.5-33.85-66.65-66.65-34.18 33.49Z" style="fill:#00de94;fill-rule:nonzero" transform="scale(.03128 .03127)"/> <path class="m-header__logo-text" d="m2900.84 1195.11 210.03-575.446h-161.58L2821.3 962.715l-126.8-343.051h-164.06L2738 1195.11h162.84ZM3916.63 808.055c-9.98-8.714-16.18-22.387-16.18-37.292 0-31.072 26.13-52.227 63.42-52.227 42.24 0 73.32 24.882 73.32 59.695v9.946h149.13c-3.73-116.835-83.3-186.46-215.03-186.46-134.2 0-222.49 73.337-222.49 182.719 0 89.489 55.95 146.659 180.26 183.982 84.48 26.053 106.87 42.252 106.87 77.032 0 32.29-26.08 54.66-63.41 54.66-45.94 0-68.34-22.37-75.77-72.07h-151.64c6.2 119.33 89.47 188.92 226.18 188.92 134.24 0 223.76-74.57 223.76-186.44 0-45.981-17.45-89.478-48.46-119.303-24.91-23.619-68.38-46.022-131.8-64.652-79.53-24.837-80.79-24.837-98.16-38.51ZM5890.05 762.052c8.69 0 21.11 1.247 33.59 2.479V602.952c-8.72-1.232-14.95-1.232-18.65-1.232-34.81 0-68.38 9.946-93.25 27.36-23.59 17.399-34.81 34.813-50.93 77.049v-84.486h-157.88v575.447h157.88V919.904c0-54.66 4.96-79.542 23.62-105.625 22.33-32.334 62.13-52.227 105.62-52.227ZM3696.68 916.183c0-185.199-128-314.444-310.72-314.444-178.98 0-304.49 126.766-304.49 306.976 0 178.995 130.5 308.235 313.22 308.235 121.78 0 222.45-63.34 279.63-175.25l-145.44-39.77c-24.84 46.01-74.54 74.58-132.97 74.58-78.31 0-136.71-49.71-150.39-129.27h449.94c1.22-11.164 1.22-27.316 1.22-31.057Zm-451.16-59.649c14.94-78.311 65.9-121.823 141.7-121.823 78.29 0 132.98 45.976 146.65 121.823h-288.35ZM4761.7 648.979c-48.46-31.086-100.68-47.238-160.36-47.238-85.75 0-141.67 27.345-188.9 90.736v-70.873h-157.85v832.776h157.85v-319.43c48.46 55.92 110.65 82.05 192.64 82.05 172.8 0 287.13-121.82 287.13-305.804 0-115.557-43.48-202.567-130.51-262.217Zm-196.36 441.211c-91.96 0-152.9-69.6-152.9-173.991 0-106.933 64.61-181.502 157.89-181.502 89.47 0 152.86 74.569 152.86 180.24 0 101.903-65.9 175.253-157.85 175.253ZM5545.84 916.183c0-185.199-128.06-314.444-310.75-314.444-178.99 0-304.5 126.766-304.5 306.976 0 178.995 130.5 308.235 313.21 308.235 121.8 0 222.46-63.34 279.68-175.25l-145.44-39.77c-24.87 46.01-74.57 74.58-133 74.58-78.28 0-136.72-49.71-150.39-129.27h449.89c1.3-11.164 1.3-27.316 1.3-31.057Zm-451.19-59.649c14.89-78.311 65.86-121.823 141.66-121.823 78.38 0 133.01 45.976 146.72 121.823h-288.38ZM6151.26 1195.67h125.29v-131.49h-27.29c-32.25 0-44.66-9.91-44.66-37.22V751.611h71.95V618.879h-71.95V465.06h-157.54v153.819h-65.75v132.732h65.75v334.929c0 76.88 29.78 109.13 104.2 109.13ZM7498.37 697.044c-73.17-65.762-143.89-95.525-229.46-95.525-178.63 0-305.15 129.003-305.15 310.099 0 174.922 128.99 303.912 303.88 303.912 86.84 0 155.07-26.05 220.82-85.6l-95.52-102.97c-40.93 35.99-70.7 48.38-112.88 48.38-90.56 0-157.51-71.94-157.51-168.68 0-94.258 64.47-164.978 151.32-164.978 45.89 0 84.34 16.129 119.07 50.862l105.43-95.5ZM6470.14 855.809c14.89-78.152 65.74-121.583 141.41-121.583 78.14 0 132.72 45.917 146.36 121.583h-287.77Zm450.26 59.549c0-184.836-127.76-313.839-310.09-313.839-178.62 0-303.89 126.518-303.89 306.371 0 178.65 130.23 307.64 312.56 307.64 121.56 0 222.04-63.27 279.1-174.9l-145.13-39.71c-24.81 45.91-74.41 74.42-132.72 74.42-78.16 0-136.44-49.59-150.09-129.002h449.02c1.24-11.146 1.24-27.264 1.24-30.98Z" style="fill-rule:nonzero" transform="scale(.03128 .03127)"/> </svg>
</div>
</a>



      <!-- Add more as needed -->

    </div>
      
      

      <a href="/sponsors/" 
         class="btn btn-primary">
        How to sponsor
      </a>
    </div>
    
</div>

  </section>
  
  
  
  
  







<script>
(function() {
  function onScroll() {
    document.querySelectorAll('.fade-in').forEach(function(el) {
      var rect = el.getBoundingClientRect();
      if (rect.top < window.innerHeight - 100) el.classList.add('visible');
    });
  }
  document.addEventListener('scroll', onScroll);
  document.addEventListener('DOMContentLoaded', onScroll);
})();
</script>

<script>
var YT_VIDEO_ID = 'wPjtwACmaUg';
var player;
function onYouTubeIframeAPIReady() {
  player = new YT.Player('yt-player', {
    width: '100%',
    height: '100%',
    videoId: YT_VIDEO_ID,
    playerVars: {
      autoplay: 1,
      controls: 0,
      modestbranding: 1,
      rel: 0,
      mute: 1,
      playsinline: 1,
      loop: 1,
      playlist: YT_VIDEO_ID,
      iv_load_policy: 3
    },
    events: {
      onReady: function(e) {
        try { e.target.mute(); e.target.playVideo(); } catch (err) {}
      },
      onStateChange: function(e) {
        if (e.data === YT.PlayerState.ENDED) {
          try { e.target.seekTo(0); e.target.playVideo(); } catch (err) {}
        }
      }
    }
  });
}
(function loadYT() {
  if (window.YT && window.YT.Player) return onYouTubeIframeAPIReady();
  var tag = document.createElement('script');
  tag.src = "https://www.youtube.com/iframe_api";
  var firstScript = document.getElementsByTagName('script')[0];
  firstScript.parentNode.insertBefore(tag, firstScript);
})();
</script>

<script>
document.addEventListener("DOMContentLoaded", () => {
  const wrapper = document.querySelector(".carousel-wrapper");
  if (!wrapper) return;

  let current = 0;
  let speed = 0.25;   // ⭐ tweak this (0.15 = slow, 0.4 = faster)
  let isPaused = false;
  let isDragging = false;

  /* -----------------------
     PAUSE ON HOVER
  ----------------------- */
  wrapper.addEventListener("mouseenter", () => isPaused = true);
  wrapper.addEventListener("mouseleave", () => isPaused = false);

  /* -----------------------
     DRAG SUPPORT (optional but premium)
  ----------------------- */
  let startX = 0;
  let scrollStart = 0;

  wrapper.addEventListener("mousedown", (e) => {
    isDragging = true;
    startX = e.pageX;
    scrollStart = wrapper.scrollLeft;
    wrapper.style.cursor = "grabbing";
  });

  window.addEventListener("mouseup", () => {
    isDragging = false;
    wrapper.style.cursor = "grab";
  });

  wrapper.addEventListener("mousemove", (e) => {
    if (!isDragging) return;
    const dx = e.pageX - startX;
    wrapper.scrollLeft = scrollStart - dx;
  });

  /* -----------------------
     AUTO SCROLL LOOP
  ----------------------- */
  function autoScroll() {
    if (!isPaused && !isDragging) {
      current += speed;
      wrapper.scrollLeft = current;

      // seamless loop (because you duplicated cards)
      if (current >= wrapper.scrollWidth / 2) {
        current = 0;
        wrapper.scrollLeft = 0;
      }
    }

    requestAnimationFrame(autoScroll);
  }

  autoScroll(); // ⭐ IMPORTANT: start animation
});
</script>
