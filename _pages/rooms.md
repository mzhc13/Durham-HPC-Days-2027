---
layout: splash
title: "Conference Rooms & Campus Map"
permalink: /rooms/
classes: [full-programme]
---

<section class="ws-hero">

<div class="ws-hero__grid"></div>

<div class="ws-hero__content">

<p class="ws-hero__eyebrow">
Durham HPC Days 2026
</p>

<h1>Conference Rooms</h1>

</div>
</section>



<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<br>
Below is an interactive map of the campus showing all main venues for the conference sessions. More details coming up soon

<div id="campus-map"></div>

---


<script>
document.addEventListener("DOMContentLoaded", function () {

  const map = L.map('campus-map').setView([54.7644, -1.5720], 17);

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; OpenStreetMap contributors'
  }).addTo(map);

  // 🏛️ ROOM MARKERS (replace coordinates with your real buildings)

  const rooms = [
    {
      name: "Mountjoy Centre: Event Space, MJC2004, MJC2006, MJC 4004, MJC4003, MJC5011",
      lat: 54.76445,
      lon: -1.5712,
      color: "green"
    },
    {
      name: "Rowan House: RH007",
      lat: 54.7642,
      lon: -1.5725,
      color: "green"
    },
    {
      name: "Computer Science Building: Rooms MCS0001, MCS2053, MCS2068 and VisLab",
      lat: 54.7635,
      lon: -1.572,
      color: "red"
    }
  ];

  rooms.forEach(r => {
    L.marker([r.lat, r.lon])
      .addTo(map)
      .bindPopup("<b>" + r.name + "</b>");
  });

});
</script>

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
  linear-gradient(
    rgba(0,42,65,0.92),
    rgba(0,42,65,0.92)
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

#campus-map {
  height: 500px;
  width: 100%;
  border-radius: 12px;
  margin: 2rem 0;
  border: 1px solid #e3e8ef;
}

.rooms-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1rem;
  margin-top: 2rem;
}

.room-card {
  background: #fff;
  border: 1px solid #dce3ec;
  border-radius: 12px;
  padding: 1rem;
}

.room-card h3 {
  margin-top: 0;
  font-size: 1rem;
  color: #002A41;
}

.room-card ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.room-card li {
  font-size: 0.85rem;
  margin-bottom: 0.4rem;
}

.room-time {
  font-size: 0.75rem;
  color: #666;
}


.room-sessions {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.room-sessions .session-card {
  margin-bottom: 0.2rem;
}

.room-time {
  font-size: 0.6rem;
  color: #444;
  margin: 0;
}

.room-sessions .speaker {
  font-size: 0.4rem;
  color: #333;
  margin: 0;
}

.rooms-selector {
  margin: 1.5rem 0;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

#room-select {
  padding: 0.6rem;
  border-radius: 8px;
  border: 1px solid #dce3ec;
  font-size: 0.9rem;
  max-width: 400px;
}

.room-display {
  margin-top: 2rem;
  padding: 1rem;
  border: 1px solid #dce3ec;
  border-radius: 12px;
  background: #fff;
}

.room-placeholder {
  color: #666;
  font-style: italic;
}

.room-display .session-card {
  margin-bottom: 0.5rem;
}

.parallax-hero {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  height: 50vh;
  background-image: url("https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/eva-blue-banner-no-title.png?raw=true");
  background-attachment: fixed;
  background-position: 120% 80%;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
}

.parallax-overlay {
  background: linear-gradient(rgba(104,36,109,0.85), rgba(70,20,75,0.85));
  color: white;
  padding: 2rem 15rem;
  text-align: center;
  border-radius: 14px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.40);
}

.parallax-hero h1 {
  font-size: 4rem;
  margin-bottom: 0.5rem;
  color: white;
}

.parallax-hero p {
  font-size: 1.3rem;
  opacity: 0.95;
}

@media (max-width: 768px) {

  /* HERO */
  .parallax-hero {
    height: 32vh;
    min-height: 180px;
    background-attachment: scroll;
    background-position: center;
  }

  .parallax-hero h1 {
    font-size: 2.2rem;
    padding: 0 1rem;
    text-align: center;
  }

  .parallax-overlay {
    padding: 1.2rem 1.5rem;
    margin: 0 1rem;
    border-radius: 10px;
  }

  .parallax-hero p {
    font-size: 1rem;
  }

}

</style>


<script>
document.addEventListener("DOMContentLoaded", function () {

  const select = document.getElementById("room-select");
  const display = document.getElementById("room-display");
  const dataBlocks = document.querySelectorAll(".room-block");

  function clearDisplay() {
    display.innerHTML = '<p class="room-placeholder">Select a room to see sessions</p>';
  }

  function showRoom(slug) {

    if (!slug) {
      clearDisplay();
      return;
    }

    const block = document.querySelector(`.room-block[data-room="${slug}"]`);

    if (!block) return;

    display.innerHTML = block.innerHTML;
  }

  select.addEventListener("change", function () {
    showRoom(this.value);
  });

});
</script>
