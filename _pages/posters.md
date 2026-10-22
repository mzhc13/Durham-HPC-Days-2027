---
layout: splash
title: "DRI Project Posters"
permalink: /posters/
---


<style>



  
  .ws-hero {
    position: relative;
    width: 100vw;
    margin-left: calc(50% - 50vw);
    height: 52vh;
    min-height: 320px;
    background-image: url("https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/eva-blue-banner-no-title.png?raw=true");
    background-attachment: fixed;
    background-position: center 60%;
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    align-items: flex-end;
    justify-content: flex-start;
    overflow: hidden;
  }

  .ws-hero__overlay {
    position: absolute;
    inset: 0;
  background: 
    linear-gradient(rgba(0,0,0,0.35), rgba(0,0,0,0.35)), /* contrast layer */
    linear-gradient(
      135deg,
rgba(120, 0, 0, 0.95) 0%,
rgba(220, 50, 50, 0.75) 60%,
rgba(120, 0, 0, 0.55) 100%
);
  }


  .ws-hero__grid {
    position: absolute;
    inset: 0;
    background-image:
   linear-gradient(rgba(255, 220, 120, 0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 220, 120, 0.06) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
  }

  .ws-hero__content {
    position: relative;
    z-index: 2;
    padding: 0 3rem 3rem;
    max-width: 860px;
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

  .ws-hero__sub {
    font-size: 1rem;
    color: rgba(255,255,255,0.60);
    font-weight: 300;
    margin: 0;
    letter-spacing: 0.01em;
  }


.description {
 

  
  text-align: center;
 
  line-height: 1.6;
  
    max-width: 700px;
  margin: 2rem auto 0.5rem;
  font-size: 1.05rem;
  color: #555;
}


.about-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.8rem;
  margin: 3rem auto 4rem;
  padding: 0 1rem;
}


.about-card {
  background: #ffffff;
  border-radius: 16px;
  padding: 1.2rem 1.3rem;
  box-shadow: 0 8px 22px rgba(0,0,0,0.05);

  display: flex;
  flex-direction: column;
  justify-content: space-between;

  min-height: 150px;

  transition: all 0.25s ease;
border-top: 6px solid #f5b800;
}


.about-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 14px 32px rgba(0,0,0,0.10);
}


.card-title {
  font-size: 1.05rem;
  font-weight: 600;
  color: #002A41;

  line-height: 1.35;
  margin-bottom: 0.8rem;


  display: -webkit-box;
  -webkit-line-clamp: 4; 
  -webkit-box-orient: vertical;
  overflow: hidden;

  min-height: 2.8em;
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
  background: #f5b800;
  transform: scale(1.05);
}


.parallax-hero {
  height: 42vh;
  background-position: center 70%;
}

.parallax-hero h1 {
  font-size: 3rem;
}




.card-details {
  margin: 0.6rem 0 1rem;
  display: flex;
  flex-direction: column;
  gap: 0.6rem;
}


.card-row {
  display: flex;
  align-items: flex-start;
  gap: 0.6rem;
}


.card-icon {
  font-size: 0.9rem;
  line-height: 1.4;
  opacity: 0.8;
  width: 18px;
  flex-shrink: 0;
}


.card-text {
  font-size: 0.82rem;
  color: #002A41;
  line-height: 1.4;
}


.card-text div {
  margin-bottom: 0.1rem;
}


.card-text {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;

  padding: 1rem 2.4rem;
  border-radius: 999px;

  font-size: 0.9rem;
  font-weight: 600;
  letter-spacing: 0.06em;

  text-decoration: none;
  cursor: pointer;

  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

/* === PRIMARY CTA (RED / HERO MATCH) === */
.btn-purple {
  background: linear-gradient(
    135deg,
    #7a0000 0%,
    #d63a3a 55%,
    #7a0000 100%
  );

  color: #ffffff !important;

  box-shadow: 
    0 10px 25px rgba(122, 0, 0, 0.35),
    inset 0 1px 0 rgba(255,255,255,0.2);
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
  margin-top: 2rem;
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
@media (max-width: 768px) {
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
}


</style>


<section class="ws-hero">
  <div class="ws-hero__overlay"></div>
  <div class="ws-hero__grid"></div>

  <div class="ws-hero__content">
    <p class="ws-hero__eyebrow">Durham HPC Days 2026</p>

    <h1>Poster Session</h1>

    <p class="ws-hero__sub">
      Join our poster session and connect with the UKRI Digital Research Infrastructure community
    </p>
  </div>
</section>
<section class="dual-cards fade-in" id="submit">

 <div class="call-for-submissions">
 
 
 <section class="fade-in">
  <h2>👥 Who is this for?</h2>

  <t style="max-width: 700px; margin: 0 auto;">
    We welcome posters from <strong>UKRI-funded DRI projects</strong> across the ecosystem,
    including research infrastructure, skills, digital platforms, HPC services,
    and software initiatives.
  </t>
</section>


<section class="fade-in">
  <h2>🤝 Why take part?</h2>

  <t style="max-width: 700px; margin: 0 auto;">
    This session is designed to be relaxed, informal, and highly interactive.
    It’s a great opportunity to share your work, meet potential collaborators,
    and connect with others across the HPC and DRI landscape.
  </t>
</section>





  <h2>📌 Bringing a poster?</h2>

  <t>
    If you're part of a <strong>UKRI-funded Digital Research Infrastructure (DRI) project</strong>,
    you’re very welcome to bring a poster and showcase your work at 
    <strong>Durham HPC Days 2026</strong>.
    <br>

    There’s no formal submission process - just let us know if you’re planning to bring a poster so we can make sure there’s space for everyone.<br><br>
  </t>

  <div class="deadline-box">
    📅 <strong>Wednesday · 16:30 - 18:00</strong><br>
    📍 Poster session & informal networking<br><br>
  </div>

  <t>
    You can explore examples of projects in the UKRI DRI landscape here: <a href="https://www.cake.ac.uk/landscape/rtp" target="_blank">
      Link to CAKE's website →
    </a>
  </t>

  <br>

  <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=i9hQcmhLKUW-RNWaLYpvlBhRpzyeDrFBkd8HIFx_xpdUOEdFSzlOUjBaUkVLQTZCMUhCWElERkJXUy4u" 
     class="btn btn-purple">
    I’m bringing a poster (Form) <span>→</span>
  </a>

  

</div>
</section>






