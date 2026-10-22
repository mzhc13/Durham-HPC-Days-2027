---
layout: splash
title: "Conference Programme – Week View"
permalink: /programme-week/
classes: [full-programme]
---

{% assign all_sessions = site.programme-2026
  | where_exp: "s", "s.start_time"
  | sort: "start_time" %}



{% assign tracks = "A,B" | split: "," %}
{% assign days_order = "Monday,Tuesday,Wednesday,Thursday,Friday" | split: "," %}
{% assign time_slots = all_sessions | map: "start_time" | uniq | sort %}

{% assign fixed_sessions = 
  "10:30|Coffee Break,12:00|Lunch,16:00|Coffee Break" | split: "," %}


{% for fs in fixed_sessions %}
  {% assign fs_parts = fs | split: "|" %}
  {% assign fs_time = fs_parts[0] %}
  {% assign fs_title = fs_parts[1] %}
  {% unless time_slots contains fs_time %}
    {% assign time_slots = time_slots | push: fs_time %}
  {% endunless %}
{% endfor %}

{% assign time_slots = time_slots | sort %}

<div class="programme-container">

<main class="programme-main">
<br> <br> 
  <h1 style="margin-left:3%"> Weekly Programme Overview</h1>

  <div class="week-grid">

    <!-- Header -->
    <div class="week-header">
      <div class="week-time-header">Time</div>
      {% for day in days_order %}
        <div class="week-day-header">{{ day }}</div>
      {% endfor %}
    </div>

    <!-- Rows by time -->
  {% for time in time_slots %}
  <div class="week-row">

    <!-- Time column -->
    <!-- Time column -->
<div class="week-time">
  {% assign start_time = time | split: "-" | first %}
  {{ start_time }}
</div>

    {% assign is_fixed = false %}
    {% assign fixed_title = "" %}
    {% for fs in fixed_sessions %}
      {% assign fs_parts = fs | split: "|" %}
      {% if fs_parts[0] == time %}
        {% assign is_fixed = true %}
        {% assign fixed_title = fs_parts[1] %}
      {% endif %}
    {% endfor %}

    {% if is_fixed %}
      <div class="week-cell coffee" style="grid-column: span 5; text-align:center;">
        <h3>{{ fixed_title }}</h3>
      </div>
    {% else %}
      <!-- Bucle normal por días -->
      {% for day in days_order %}
        {% assign cell_sessions = all_sessions
          | where: "day", day
          | where: "start_time", time %}

        <div class="week-cell">
          {% if cell_sessions.size == 0 %}
            <span class="empty">–</span>
          {% else %}
          {% assign cell_sessions = cell_sessions | sort: "track" %}

{% for s in cell_sessions %}
  <div class="session-card {{ s.category | downcase }}">
    <h3>
      <a href="{{ s.url | relative_url }}">
        {% if s.track %}{% endif %}
        {{ s.title }}
      </a>
    </h3>
    {% if s.speaker %}<p class="speaker">{{ s.speaker }}</p>{% endif %}
    {% if s.room %}<p class="room">Room: {{ s.room }}</p>{% endif %}
  </div>
{% endfor %}

          {% endif %}
        </div>
      {% endfor %}
    {% endif %}

  </div>
{% endfor %}



  </div>

</main>
</div>

<style>


.full-programme .page__inner-wrap,
.full-programme .page__content,
.page__inner-wrap,
.page__content {
  max-width: 100% !important;
  width: 100% !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
  margin-left: 0 !important;
  margin-right: 0 !important;
}


.full-programme .page__content section {
  padding-left: 0 !important;
  padding-right: 0 !important;
}

.programme-container {
  width: 100%;
  padding: 0 !important;
  margin: 0 !important;
}

.session-card.coffee {
  background-color: #F8FAFC; 
  border-left-color: #F8FAFC;
}

.session-card.coffee h3 a {
  color: #002A41 !important;
  text-align: center;
}


/* Layout */
.programme-container {
  width: 100%;
  max-width: 100% !important;
  padding: 0;    
  margin: 0;  
}

/* Weekly grid */
.week-grid {
  display: grid;
  gap: 0.5rem;
}

/* Header + rows */
.week-header,
.week-row {
  display: grid;
  grid-template-columns: 90px repeat(5, 1fr);
  gap: 0.5rem;
}

/* Headers */
.week-day-header {
  font-weight: 700;
  text-align: center;
  background: #002A41;
  color: #ffffff;
  padding: 0.5rem;
  border-radius: 8px;
  font-size: 0.9rem;
}

.week-time-header {
  font-weight: 700;
  text-align: center;
  background: #002A41;
  color: #ffffff;
  padding: 0.5rem;
  border-radius: 8px;
  font-size: 0.9rem;
}

/* Time column */
.week-time {
  font-weight: 700;
  text-align: center;
  background: #f4f6f8;
  border-radius: 8px;
  padding: 0.5rem;
  font-size: 0.85rem;
}

/* Cells */
.week-cell {
  background: #ffffff;
  border: 1px solid #dce3ec;
  border-radius: 8px;
  padding: 0.3rem;
  min-height: 90px;
}

/* Empty cells */
.week-cell .empty {
  display: block;
  text-align: center;
  color: #ccc;
}

/* Session cards */
.week-cell .session-card {
  margin-bottom: 0.3rem;
  padding: 0.4rem;
  border-left: 4px solid;
  border-radius: 6px;
  color: #002A41;
}

.week-cell .session-card h3 {
  font-size: 0.9rem;
  margin: 0;
  color: #002A41 !important;
}

.session-card.opening { background-color: #68246D; color: #fff; border-left-color: #68246D; }
.session-card.opening h3, .session-card.opening .speaker, .session-card.opening .room { color: #002A41; }




.session-card.workshop { background-color: #FFF8E1; border-left-color: #FFC107; }
.session-card.talk { background-color: #C8DCE6; border-left-color: #3D6F89; }
.session-card.session { background-color: #F3E5F5; border-left-color: #9C27B0; }
.session-card.tutorial { background-color: #E6DDC0; border-left-color: #DACDA2; }
.session-card.coffee { background-color: #F8FAFC; border-left-color: #F8FAFC; }
.session-card.social { background-color: #F8FAFC; border-left-color: #F8FAFC; }

.session-card .speaker { font-size: 0.7rem; color: #333; margin:0; }
.session-card .room { font-size: 0.6rem; color: #444; margin:0; }

.week-cell .session-card h3 a {
  color: inherit !important;
}
.session-card.opening h3 a {
  color: #ffffff !important;
}

.session-card.workshop h3 a,
.session-card.talk h3 a,
.session-card.session h3 a,
.session-card.tutorial h3 a,

.session-card.social h3 a {
  color: #002A41 !important;
}

.week-cell.coffee {
  display: flex;
  align-items: center;  
  justify-content: center;
  padding: 0.3rem;  
  min-height: 70px;
  margin-top: 0; 
}

.week-cell.coffee h3 {
  margin: 0; 
  font-size: 0.95rem;
}


.week-cell .session-card {
  transition: 
    background-color 0.2s ease,
    transform 0.15s ease,
    box-shadow 0.15s ease;
}

.week-cell .session-card:hover {
  filter: brightness(1) saturate(1.4);
  transform: scale(1.03);
  box-shadow: 0 6px 16px rgba(0,0,0,0.25);
  cursor: pointer;
}





@media (max-width: 900px) {
  .week-grid { overflow-x: auto; }
  .week-header, .week-row { grid-template-columns: 80px repeat(5, minmax(200px, 1fr)); }
}

</style>

