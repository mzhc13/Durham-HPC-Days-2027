---
layout: splash
title: "Conference Rooms & Campus Map"
permalink: /rooms-draft/
classes: [full-programme]
---

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

# Conference Rooms

Below is an interactive map of the campus showing all main venues for the conference sessions.

<div id="campus-map"></div>

---
## 📍 Rooms Overview

{% assign all_sessions = site.programme-days-2026 | where_exp: "s", "s.room" %}
{% assign rooms = all_sessions | map: "room" | uniq | sort %}

<div class="rooms-selector">

  <label for="room-select"><strong>Select a room:</strong></label>

  <select id="room-select">
    <option value="">-- Choose a room --</option>

    {% for room in rooms %}
      <option value="{{ room | slugify }}">{{ room }}</option>
    {% endfor %}
  </select>

</div>

<div id="room-display" class="room-display">
  <p class="room-placeholder">Select a room to see sessions</p>
</div>

<!-- Hidden data store -->
<div id="room-data" style="display:none;">

  {% for room in rooms %}
    <div class="room-block" data-room="{{ room | slugify }}">

      <h3>{{ room }}</h3>

      {% assign room_sessions = all_sessions | where: "room", room | sort: "start_time" %}

      {% for s in room_sessions %}
        <div class="session-card {{ s.category | downcase }}">

          <h3>
            <a href="{{ s.url | relative_url }}">
              {{ s.title }}
            </a>
          </h3>

          {% if s.start_time %}
            <p class="room-time">{{ s.start_time }}</p>
          {% endif %}

          {% if s.lead or s.instructor or s.facilitator %}
            <p class="speaker">

              {% if s.lead %}
                <strong>Lead{% if s.lead contains "," %}s{% endif %}:</strong>
                {{ s.lead }}
              {% endif %}

              {% if s.lead and s.instructor %} · {% endif %}

              {% if s.instructor %}
                <strong>Instructor{% if s.instructor contains "," %}s{% endif %}:</strong>
                {{ s.instructor }}
              {% endif %}

              {% if s.facilitator %}
                <strong>Facilitator{% if s.facilitator contains "," %}s{% endif %}:</strong>
                {{ s.facilitator }}
              {% endif %}

            </p>
          {% endif %}

        </div>
      {% endfor %}

    </div>
  {% endfor %}

</div>

<script>
document.addEventListener("DOMContentLoaded", function () {

  const map = L.map('campus-map').setView([54.7644, -1.5720], 17);

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; OpenStreetMap contributors'
  }).addTo(map);

  // 🏛️ ROOM MARKERS (replace coordinates with your real buildings)

  const rooms = [
    {
      name: "Mountjoy Centre: Event Space, MJC2004, MJC2006, MJC5011",
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
      name: "Computer Science Building: Rooms MCS0001, MCS2068 and VisLab",
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
