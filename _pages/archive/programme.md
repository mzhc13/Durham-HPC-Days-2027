---
layout: splash
title: "Conference Programme"
permalink: /programme/
classes: [full-programme]
---

{% assign sessions = site.programme | sort: "start_time" %}
{% assign tracks = "A,B" | split: "," %}
{% assign days_order = "Monday,Tuesday,Wednesday,Thursday,Friday" | split: "," %}

<div class="programme-container">


<aside class="programme-sidebar">
  <h3>Programme</h3>
  <ul class="accordion">
    {% for current_day in days_order %}
    
    {% assign day_sessions = sessions | where: "day", current_day %}
{% assign fixed_events = site.data.fixed_events %}
{% assign combined = day_sessions | concat: fixed_events %}
{% assign day_sessions = combined | sort: "start_time" %}


      {% if day_sessions != empty %}
        <li class="accordion-item">
          <div class="accordion-header">
            <span class="arrow">&gt;</span> <span class="day-name">{{ current_day }}</span>
          </div>
          <ul class="accordion-content">
            {% for session in day_sessions %}
              <li>
                <a href="#{{ session.id | default: session.title | slugify }}">
                  {{ session.start_time }} - {{ session.title }}
                </a>
              </li>
            {% endfor %}
          </ul>
        </li>
      {% endif %}
    {% endfor %}
  </ul>
 
</aside>
  <!-- Main content -->
  <main class="programme-main">
    {% for current_day in days_order %}    {% assign day_sessions = sessions | where: "day", current_day %}
    {% assign fixed_events = site.data.fixed_events %}
    {% assign combined = day_sessions | concat: fixed_events %}
    {% assign day_sessions = combined | sort: "start_time" %}
  {% if day_sessions != empty %}
    <section class="programme-day expanded" id="{{ current_day | downcase }}">
      <h2 class="day-toggle">
  <span class="arrow">&gt;</span> {{ current_day }}
</h2>
<div class="programme-grid">
          {% assign grouped_by_time = day_sessions | group_by: "start_time" %}
          {% for time_slot in grouped_by_time %}
            {% assign first_session = time_slot.items | first %}
            <div class="programme-time">
              <div class="time-label">
                {% if first_session.start_time and first_session.end_time %}
                  {{ first_session.start_time }}<br>–<br>{{ first_session.end_time }}
                {% else %}
                  {{ first_session.start_time }}
                {% endif %}
              </div>
              {% assign session_count = time_slot.items | size %}

                {% if session_count == 1 %}
                  <!-- 🔹 Solo una sesión: ocupa todo el ancho -->
                  {% assign this_session = time_slot.items | first %}
                  {% assign category_class = this_session.category | downcase %}
                  {% if this_session.part_of %}
                    {% assign category_class = category_class | append: " split-session" %}
                  {% endif %}
                  <div class="session-card full-width {{ category_class }}"
                       id="{{ this_session.id | default: this_session.title | slugify }}"
                       {% if this_session.part_of %} data-part="{{ this_session.part_of }}" {% endif %}>
                    <h3><a href="{{ this_session.url | relative_url }}">{{ this_session.title }}</a></h3>

                    {% if this_session.speaker %}
                      <p class="speaker">{{ this_session.speaker }}</p>
                    {% endif %}

                    {% if this_session.abstract %}
                      {% assign plain_abstract = this_session.abstract | strip_html | strip_newlines | truncate: 90, "..." %}
                      <p class="abstract">{{ plain_abstract }}</p>
                      <a class="read-more" href="{{ this_session.url | relative_url }}">Read more →</a>
                    {% endif %}

                    {% if this_session.room %}
                      <p class="room">Room: {{ this_session.room }}</p>
                    {% endif %}
                  </div>

                {% else %}
                  <!-- 🔹 Dos o más sesiones (una por track) -->
                  {% for track in tracks %}
                    {% assign this_session = time_slot.items | where: "track", track | first %}
                    {% if this_session %}
                      {% assign category_class = this_session.category | downcase %}
                      {% if this_session.part_of %}
                        {% assign category_class = category_class | append: " split-session" %}
                      {% endif %}
                      <div class="session-card {{ category_class }}"
                           id="{{ this_session.id | default: this_session.title | slugify }}"
                           {% if this_session.part_of %} data-part="{{ this_session.part_of }}" {% endif %}>
                        <h3><a href="{{ this_session.url | relative_url }}">{{ this_session.title }}</a></h3>

                        {% if this_session.speaker %}
                          <p class="speaker">{{ this_session.speaker }}</p>
                        {% endif %}

                        {% if this_session.abstract %}
                          {% assign plain_abstract = this_session.abstract | strip_html | strip_newlines | truncate: 90, "..." %}
                          <p class="abstract">{{ plain_abstract }}</p>
                          <a class="read-more" href="{{ this_session.url | relative_url }}">Read more →</a>
                        {% endif %}

                        {% if this_session.room %}
                          <p class="room">Room: {{ this_session.room }}</p>
                        {% endif %}
                      </div>
                    {% else %}
                      <div class="session-card empty"><p class="no-session">–</p></div>
                    {% endif %}
                  {% endfor %}
                {% endif %}
              </div> <!-- programme-time -->
            {% endfor %}
          </div> <!-- programme-grid -->
        </section>
      {% endif %}
    {% endfor %}

   
  </main>
</div>
     
     
     
<style>

.programme-container {
  display: flex;
  gap: 2rem;
}

.programme-container {
  display: flex;
  gap: 1rem;
   padding-top: 4rem; 
}


.programme-sidebar {
  flex: 0 0 250px;
  background: #f4f6f8;
  padding: 1rem;
  border-radius: 8px;
  position: sticky;
  top: 3.5rem;
  max-height: calc(100vh - 4rem); 
  overflow-y: scroll; 
  overflow-x: hidden;
  scrollbar-width: thin; 
  scrollbar-color: #68246D;
}
.programme-note {
  background: #002A41;
  color: white;
  text-align: center;
  padding: 1rem;
  border-radius: 8px;
  margin-top: 2rem;
  font-style: italic;
  font-size: 0.95rem;
  opacity: 0.9;
  transition: opacity 0.3s ease;
}

.programme-note:hover {
  opacity: 1;
}

.programme-main {
  flex: 1;
}

.programme-main {
  flex: 1;
}


.full-programme .page__inner-wrap,
.full-programme .page__content {
  max-width: none !important;
  width: 100% !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
}

.programme-day {
 margin: 0 0 1rem 0; 
  padding: 0.5rem 3%;  
}

.programme-day h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
  color: #002A41;
  border-bottom: 2px solid #dce3ec;
  padding-bottom: 0.3rem;
  margin: 0 0 0.5rem 0; 
  padding-bottom: 0.3rem;
}


.programme-grid {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.programme-time {
  display: grid;
  grid-template-columns: 0.75fr 2.25fr 2.25fr;
  gap: 0.5rem;
  align-items: stretch;
  background: #f8fafc;
  border-radius: 10px;
  padding: 0.5rem;
  box-shadow: 0 1px 4px rgba(0,0,0,0.08);
}

.time-label {
  font-weight: 800;
  font-size: 0.8rem;
  color: #ffffff;
  background: #002A41;
  border-radius: 8px;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.session-card {
  background: #ffffff;
  border: 1px solid #dce3ec;
  border-radius: 8px;
  padding: 0.5rem;
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  
}

.session-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 10px rgba(0,0,0,0.08);
}

.session-card h3 {
  font-size: 1.15rem;
  color: #002A41;
  margin-bottom: 0rem;
   margin-top: 0rem;
}

.session-card h3 a {
  text-decoration: none;
  color: inherit;
    margin-bottom: 0rem;
   margin-top: 0rem;
}

.session-card h3 a:hover {
  text-decoration: underline;
    margin-bottom: 0rem;
   margin-top: 0rem;
}

.speaker {
    color: #555;
  margin-bottom: 0rem;
   margin-top: 0rem;
}

.session-card .speaker {
font-size: 1rem;
  color: #333;
  margin-bottom: 0rem;
    margin-top: 0rem;
    text-align: left;
 font-style: normal !important;
    
}


.session-card .abstract {
font-size: 0.6rem;
  color: #333;
  margin-bottom: 0rem;
    margin-top: 0rem;
    text-align: left;
    
}


.session-card.full-width {
  grid-column: 2 / span 2;
}

.session-card.full-width h3 {
  font-size: 1rem;
  color: #002A41;
  margin-bottom: 0rem;
   margin-top: 0.1rem;
   text-align: center;
}


.session-card .room {
  font-size: 0.75rem;
  color: #444;
  line-height: 1.2;
  margin-top: 0rem;
    margin-bottom: 0rem;
}

.session-card .read-more {
  font-size: 0.9rem;
  color: #68246D;
  text-decoration: none;
  font-weight: 600;
  margin-bottom: 0rem;
    margin-top: 0rem;
}

.read-more:hover {
  text-decoration: underline;
}

.no-session {
  text-align: center;
  color: #aaa;
  margin-top: 1.5rem;
}

/* Responsive */
@media (max-width: 900px) {
  .programme-time {
    grid-template-columns: 1fr;
  }

  .time-label {
    margin-bottom: 0.5rem;
  }
}






.programme-sidebar .accordion {
  list-style: none;
  padding-left: 0;
  margin: 0;
}

.accordion-item {
  margin-bottom: 0.5rem;
}

.accordion-header {
  cursor: pointer;
  display: flex;
  align-items: center;
  font-weight: 600;
  color: #002A41;
  padding: 0.3rem 0.5rem;
  user-select: none;
  border-radius: 6px;
  transition: color 0.2s;
  font-size: 0.75rem;
}

.accordion-header {
  display: block;
  font-weight: 600;
  color: #002A41;
  padding: 0.3rem 0.5rem;
  font-size: 1rem;
  white-space: nowrap;      
  overflow: hidden;         
  text-overflow: ellipsis;  
  max-width: 200px;
}

.accordion-header:hover {
  color: #68246D;
}

.accordion-item.active .accordion-header {
  color: #68246D; 
}

.arrow {
  display: inline-block;
  margin-right: 0.5rem;
  transition: transform 0.3s;
}

.accordion-item.active .arrow {
  transform: rotate(90deg);
}

.accordion-content {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease;
  margin-left: 0.5rem;
  line-height: 0.5rem;
}

.accordion-content li a {
  display: block;
  padding: 0.1rem 0;
  text-decoration: none;
  color: #002A41;
  font-size: 0.5rem;
}

.accordion-content li a:hover {
  text-decoration: underline;
}

.accordion-item.active .accordion-content {
  max-height: 500px;
}



/*COLOUR CODED*/
.session-card.workshop {
  background-color: #FFF8E1;
  border-left: 4px solid #FFC107;
  font-colour:
}



.session-card.opening {
  background-color: #68246D;
  border-left: 4px solid #68246D;
 
}

.session-card.talk {
  background-color: #C8DCE6;
  border-left: 4px solid #3D6F89;
  font-colour:
}



/*OPENING SESSIONS*/
.session-card.opening h3 {
  font-size: 1rem;
  color: #ffffff;
  margin-bottom: 0rem;
   margin-top: 0.1rem;
   text-align: left;
}

.session-card.opening .speaker {
	font-size: 1rem;
  color: #ffffff;
  margin-bottom: 0rem;
    margin-top: 0rem;
    text-align: left;
 font-style: normal !important;
}
.session-card.opening .room {
  font-size: 0.75rem;
  color: #ffffff;
  line-height: 1.2;
  margin-top: 0rem;
    margin-bottom: 0rem;
}


/*WORKSHOP SESSIONS*/
.session-card.workshop h3 {
  font-size: 1rem;
  color: #002A41;
  margin-bottom: 0rem;
   margin-top: 0.1rem;
   text-align: left;
}

.session-card.talk h3 {
  font-size: 1rem;
  color: #002A41;
  margin-bottom: 0rem;
   margin-top: 0.1rem;
   text-align: left;
}



/*SESSION SESSIONS*/
.session-card.session h3 {
  font-size: 1rem;
  color: #002A41;
  margin-bottom: 0rem;
   margin-top: 0.1rem;
   text-align: left;
}


/*COFFEE SESSIONS*/
.session-card.coffee h3 {
  font-size: 1rem;
  color: #002A41;
  margin-bottom: 0rem;
   margin-top: 0.75rem;
   text-align: center;
}

.session-card.coffee {
  background-color: #F8FAFC; 
  border-left: 4px solid #F8FAFC;
  border-color: #F8FAFC;
}


.session-card.coffee .time-label {
  font-weight: 800;
  font-size: 0.8rem;
  color: #ffffff;
  background: #ffffff;
  border-radius: 8px;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.programme-time:has(.session-card.coffee) .time-label {
  background: #F8FAFC; 
  color: #002A41;      
}



/*SOCIAL SESSIONS*/
.session-card.social h3 {
  font-size: 1rem;
  color: #002A41;
  margin-bottom: 0rem;
   margin-top: 0.75rem;
   text-align: center;
}



.session-card.social .time-label {
  font-weight: 800;
  font-size: 0.8rem;
  color: #ffffff;
  background: #ffffff;
  border-radius: 8px;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.programme-time:has(.session-card.social) .time-label {
  background: #F8FAFC; 
  color: #002A41;      
}


/*TUTORIAL SESSIONS*/
.session-card.tutorial h3 {
  font-size: 1rem;
  color: #002A41;
  margin-bottom: 0rem;
   margin-top: 0.1rem;
   text-align: left;
}

.session-card.tutorial {
  background-color: #E6DDC0;
  border-left: 4px solid #DACDA2;
}

.session-card.session {
  background-color: #F3E5F5;
  border-left: 4px solid #9C27B0;
}

.session-card.social {
   background-color: #F8FAFC;
  border-left: 4px solid #F8FAFC;
  border-color: #F8FAFC;
}

.session-card.coffee {
  background-color: #F8FAFC; 
  border-left: 4px solid #F8FAFC;
  border-color: #F8FAFC;
}



.session-card.split-session {
  border: 2px solid #DACDA2;
  transition: box-shadow 0.3s ease, transform 0.2s ease;
}

.session-card.split-session:hover,
.session-card.split-session.hover-pair {
  box-shadow: 0 0 12px #DACDA2;
  transform: scale(1.05);
}

@media (max-width: 768px) {
   .programme-sidebar {
    display: none;
  }

  .programme-main {
    flex: 1 1 100%;
    padding: 0 1rem;
  }
  
  .programme-time {
    display: grid;
    grid-template-columns: 0.75fr 2.25fr 2.25fr;
    gap: 0.5rem;
    align-items: stretch; 
padding: 0.5rem;
  }

  .time-label,
    .time-label {
    text-align: center;
    background: #002A41;
    color: #fff;    
    border-radius: 8px;
     padding-left: 0.5rem; 
    padding-right: 0.5rem;
    padding-top: 0.5rem;  
      padding-bottom: 0.5rem; 
}
  }
  .session-card {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    padding: 0.5rem;
  }

 .programme-day .programme-grid {
    max-height: 0;             
    overflow: hidden;
    transition: max-height 0.4s ease;
  }

  .programme-day.expanded .programme-grid {
    max-height: 2000px;        
  }
  .day-toggle {
    cursor: pointer;
    display: flex;
    align-items: center;
    font-size: 1.2rem;
    background: #f4f6f8;
    padding: 0.5rem 1rem;
    border-radius: 8px;
    margin-bottom: 0.5rem;
     margin: 0 0 1rem 0; 
  padding: 0.5rem 3%;  
  }

  .day-toggle .arrow {
    display: inline-block;
    margin-right: 0.5rem;
    transition: transform 0.3s ease;
  }

  .programme-day.expanded .arrow {
    transform: rotate(90deg);
  }

  .programme-day.expanded .arrow {
    transform: rotate(90deg);
  }
 .programme-day .programme-grid {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.4s ease;
  }
  .programme-day.expanded .programme-grid {
    max-height: 2000px;        
  }
}

}

@media (min-width: 769px) {
  .day-toggle .arrow {
    display: none;
  }
    .programme-day {
    max-height: none; 
  }
}
</style>

<script>
document.querySelectorAll('.accordion-header').forEach(header => {
  header.addEventListener('click', () => {
    const item = header.parentElement;
    item.classList.toggle('active');
  });
});
</script>

<script>
document.addEventListener("DOMContentLoaded", function() {

  function initAccordion() {
    document.querySelectorAll('.day-toggle').forEach(header => {
      // Evitar añadir múltiples veces
      header.removeEventListener('click', toggleDay);
      header.addEventListener('click', toggleDay);
    });
  }

  function toggleDay(event) {
    const daySection = event.currentTarget.closest('.programme-day');
    daySection.classList.toggle('expanded');
  }

  initAccordion();

});
</script>
