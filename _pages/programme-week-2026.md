---
layout: splash
title: "Conference Programme – Week View"
permalink: /programme-week-2026/
classes: [full-programme]
---

{% assign all_sessions = site.programme-days-2026
  | where_exp: "s", "s.start_time"
  | sort: "start_time" %}

{% assign days_order = "Monday 15 June,Tuesday 16 June,Wednesday 17 June,Thursday 18 June,Friday 19 June" | split: "," %}

{% assign time_slots = all_sessions | map: "start_time" | uniq | sort %}

{% assign fixed_sessions = "10:30|Coffee Break,12:00|Lunch,14:30|Break,16:00|Coffee Break" | split: "," %}

{% for fs in fixed_sessions %}
  {% assign fs_parts = fs | split: "|" %}
  {% assign fs_time = fs_parts[0] %}
  {% unless time_slots contains fs_time %}
    {% assign time_slots = time_slots | push: fs_time %}
  {% endunless %}
{% endfor %}

{% assign time_slots = time_slots | sort %}


<link rel="stylesheet" href="{{ '/assets/css/hpc-days.css' | relative_url }}">


<div class="hpc hpc-programme">


  <!-- PROGRAMME -->
  <section class="hpc-section hpc-programme-section">
    <div class="hpc-in">

      <div class="programme-intro">
        <div>
          <p class="programme-eyebrow">Plan your week</p>
          <h2>Week at a glance</h2>
          <p class="hpc-sub">
            Select a session type to highlight matching sessions throughout
            the timetable. Select it again, or click elsewhere, to reset.
          </p>
        </div>

        <div class="programme-links">
          <a href="{{ '/rooms/' | relative_url }}">🗺️ Room map</a>
          <a href="https://raw.githubusercontent.com/hpc-days/Durham-HPC-Days-2026/main/assets/images/booklet-hpcdays-26.pdf">
            📖 Full booklet
          </a>
          <a href="https://raw.githubusercontent.com/hpc-days/Durham-HPC-Days-2026/main/assets/images/summary-booklet-hpcdays-26.pdf">
            📄 Quick overview
          </a>
        </div>
      </div>

      <div class="my-timetable-toolbar">
  <div class="my-timetable-intro">
    <strong>My Timetable</strong>
    <span id="my-timetable-count" aria-live="polite">
      0 sessions selected
    </span>
  </div>

  <div class="my-timetable-actions">
    <button type="button" id="toggle-my-timetable" class="hpc-btn">
      View my timetable
    </button>
   <button type="button" id="print-my-timetable" class="hpc-btn">
      Print schedule
    </button> 
    <button type="button" id="clear-my-timetable" class="hpc-btn">
      Clear selections
    </button>
  </div>
  <p id="my-timetable-status" role="status" aria-live="polite"></p>
</div>

      <!-- SESSION TYPE FILTERS -->
      <div class="programme-legend" aria-label="Filter sessions by type">
        <button class="legend-item keynote" type="button"
                data-category="keynote" aria-pressed="false">
          <span class="legend-colour"></span> Keynotes
        </button>
        <button class="legend-item tutorial" type="button"
                data-category="tutorial" aria-pressed="false">
          <span class="legend-colour"></span> Tutorials
        </button>
        <button class="legend-item talk" type="button"
                data-category="talk" aria-pressed="false">
          <span class="legend-colour"></span> Talks
        </button>
        <button class="legend-item workshop" type="button"
                data-category="workshop" aria-pressed="false">
          <span class="legend-colour"></span> Workshops
        </button>
        <button class="legend-item meeting" type="button"
                data-category="meeting" aria-pressed="false">
          <span class="legend-colour"></span> Meetings
        </button>
        <button class="legend-item social" type="button"
                data-category="social" aria-pressed="false">
          <span class="legend-colour"></span> Socials
        </button>
        <button class="legend-item poster" type="button"
                data-category="poster" aria-pressed="false">
          <span class="legend-colour"></span> Other
        </button>
      </div>

      <p class="programme-filter-status" aria-live="polite">
        Showing all session types.
      </p>

      <!-- HORIZONTAL SCROLL CONTAINER -->
      <div class="programme-scroll" tabindex="0"
           role="region" aria-label="Weekly programme timetable. Scroll horizontally to view all five days.">

        <div class="week-grid">

          <!-- DAY HEADERS -->
          <div class="week-header">
            <div class="week-time-header">Time</div>
            {% for day in days_order %}
              <div class="week-day-header">
                <span class="day-name">{{ day | split: " " | first }}</span>
                <span class="day-date">
                  {{ day | remove_first: day | split: " " | join: " " }}
                  {% assign day_parts = day | split: " " %}
                  {{ day_parts[1] }} {{ day_parts[2] }}
                </span>
              </div>
            {% endfor %}
          </div>

          <!-- TIMETABLE ROWS -->
          {% for time in time_slots %}

            {% assign is_fixed = false %}
            {% assign fixed_title = "" %}

            {% for fs in fixed_sessions %}
              {% assign fs_parts = fs | split: "|" %}
              {% if fs_parts[0] == time %}
                {% assign is_fixed = true %}
                {% assign fixed_title = fs_parts[1] %}
              {% endif %}
            {% endfor %}

            {% assign has_content = false %}

            {% for day in days_order %}
              {% assign day_name = day | split: " " | first %}
              {% assign cell_sessions = all_sessions
                | where: "day", day_name
                | where: "start_time", time %}
              {% if cell_sessions.size > 0 %}
                {% assign has_content = true %}
              {% endif %}
            {% endfor %}

            {% if has_content or is_fixed %}
              <div class="week-row">

                <div class="week-time">
                  <span>{{ time | split: "-" | first }}</span>
                </div>

                {% if is_fixed %}
                  <div class="week-cell fixed-session"
                       style="grid-column: span 5;">
                    <span class="fixed-icon" aria-hidden="true">
                      {% if fixed_title == "Lunch" %}☕
                      {% else %}◷{% endif %}
                    </span>
                    <span>{{ fixed_title }}</span>
                  </div>

                {% else %}

                  {% for day in days_order %}
                    {% assign day_name = day | split: " " | first %}
                    {% assign cell_sessions = all_sessions
                      | where: "day", day_name
                      | where: "start_time", time %}

                    <div class="week-cell">
                      {% if cell_sessions.size == 0 %}
                        <div class="empty-cell" aria-hidden="true"></div>
                      {% else %}
                        {% assign cell_sessions = cell_sessions | sort: "track" %}

                        {% for s in cell_sessions %}
                          {% assign category = s.category | downcase | strip %}

                         <article class="session-card {{ category }}"
                        data-session-category="{{ category }}"
                        data-session-id="{{ s.url | default: s.title | slugify }}"
                        {% if s.start_time %}
                        data-start="{{ s.start_time | date: '%Y-%m-%dT%H:%M:%S' }}"
                        {% endif %}
                        {% if s.end_time %}
                        data-end="{{ s.end_time | date: '%Y-%m-%dT%H:%M:%S' }}"
                        {% endif %}>

                            <div class="session-header">

                              {% if s.category %}
                                <span class="session-category category-{{ category | replace: ' ', '-' }}">
                                  {% if category == "poster" %}
                                    Other
                                  {% else %}
                                    {{ s.category | capitalize }}
                                  {% endif %}
                                </span>
                              {% endif %}

                              <h3 class="session-title">
                                <a href="{{ s.url | relative_url }}">
                                  {{ s.title }}
                                </a>
                              </h3>

                              {% if s.room or s.lead or s.instructor or s.facilitator or s.speaker or s.hybrid %}
                                <div class="session-meta">

                                  {% if s.room %}
                                    <div class="meta-line room">
                                      <span aria-hidden="true"></span>
                                      <span>{{ s.room }}</span>
                                    </div>
                                  {% endif %}

                                  {% if s.lead %}
                                    <div class="meta-line">
                                      <span class="meta-label">Lead</span>
                                      <span>{{ s.lead }}</span>
                                    </div>
                                  {% endif %}

                                  {% if s.instructor %}
                                    <div class="meta-line">
                                      <span class="meta-label">Instructor</span>
                                      <span>{{ s.instructor }}</span>
                                    </div>
                                  {% endif %}

                                  {% if s.facilitator %}
                                    <div class="meta-line">
                                      <span class="meta-label">Facilitator</span>
                                      <span>{{ s.facilitator }}</span>
                                    </div>
                                  {% endif %}

                                  {% if s.speaker and category == "keynote" %}
                                    <div class="meta-line">
                                      <span class="meta-label">Speaker</span>
                                      <span>{{ s.speaker }}</span>
                                    </div>
                                  {% endif %}

                                  {% if s.hybrid %}
                                    <span class="hybrid-link">
                                      <span aria-hidden="true">↗</span>
                                      Available online
                                    </span>
                                  {% endif %}

                                </div>
                              {% endif %}

                            </div>
                          </article>
                        {% endfor %}
                      {% endif %}
                    </div>
                  {% endfor %}

                {% endif %}
              </div>
            {% endif %}
          {% endfor %}

        </div>
      </div>

      <p class="programme-scroll-note">
        On smaller screens, swipe horizontally to explore the full week.
      </p>

      <div class="programme-footer">
        <span class="programme-footer-mark" aria-hidden="true">✳</span>
        <p>
          Need more detail? Check the
          <a href="https://raw.githubusercontent.com/hpc-days/Durham-HPC-Days-2026/main/assets/images/booklet-hpcdays-26.pdf">
            full programme booklet
          </a>
          or use the room map to plan your journey between sessions.
        </p>
      </div>

    </div>
  </section>
</div>

<style>
/* ==========================================================================
   DURHAM HPC DAYS 2026 — WEEKLY PROGRAMME
   Uses shared .hpc design tokens. All styles are page-scoped.
   ========================================================================== */

.hpc-programme {
  --programme-time-width: 76px;
  --programme-gap: 10px;
  --programme-day-width: 205px;
  --programme-keyline: rgba(255,255,255,.08);
  background: var(--bg);
  color: var(--text);
}
.hpc-programme .hpc-in {
  width: min(98%, 1800px);
  max-width: 1800px;
  margin-inline: auto;
}

/* Page header refinements */
.hpc-programme .hpc-pagehead {
  padding: 48px 0 54px;
}

.hpc-programme .hpc-host {
  margin: 0 0 12px !important;
}

.hpc-programme .hpc-pagehead h1 {
  max-width: 900px;
}

.hpc-programme .hpc-pagehead .hpc-lede {
  max-width: 760px;
}

.hpc-programme .hpc-facts {
  gap: 18px 42px;
}

.hpc-programme .hpc-actions {
  gap: 10px;
}

.hpc-programme .hpc-btn {
  font-family: inherit;
}

/* Main section */
.hpc-programme-section {
  padding: 46px 0 64px;
}

.hpc-programme .programme-intro {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  gap: 24px;
  margin-bottom: 26px;
}

.hpc-programme .programme-intro h2 {
  margin-bottom: 10px;
  border-bottom: 0 !important;
}

.hpc-programme .programme-intro .hpc-sub {
  max-width: 650px;
  margin-bottom: 0 !important;
}

.hpc-programme .programme-eyebrow {
  margin-bottom: 8px;
  color: var(--purple-light);
  font-size: 13px;
  font-weight: 800;
  letter-spacing: .12em;
  text-transform: uppercase;
}

.hpc-programme .programme-links {
  display: flex;
  flex-wrap: wrap;
  gap: 8px 18px;
  padding-bottom: 4px;
}

.hpc-programme .programme-links a {
  font-size: 14px;
  font-weight: 700;
  text-decoration: none;
  white-space: nowrap;
}

.hpc-programme .programme-links a:hover {
  text-decoration: underline;
}

/* Category colours */
.hpc-programme {
  --p-keynote: var(--s-keynote);
  --p-tutorial: var(--s-tutorial);
  --p-talk: var(--s-talk);
  --p-workshop: var(--s-workshop);
  --p-meeting: var(--s-meeting);
  --p-social: var(--s-social);
  --p-other: #C2A8F5;
}

.hpc-programme .programme-legend {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin: 0 0 8px;
  padding: 0;
  background: transparent;
  border: 0;
  border-radius: 0;
  box-shadow: none;
}

.hpc-programme .legend-item {
  display: inline-flex;
  align-items: center;
  gap: 9px;
  min-height: 38px;
  padding: 7px 13px;
  color: var(--muted);
  background: var(--card);
  border: 1px solid var(--line);
  border-radius: 5px;
  font: inherit;
  font-size: 13px;
  font-weight: 700;
  cursor: pointer;
  transition: background .2s, color .2s, border-color .2s, transform .2s;
}

.hpc-programme .legend-item:hover {
  transform: translateY(-2px);
  color: #fff;
  border-color: var(--purple-light);
  box-shadow: none;
}

.hpc-programme .legend-colour {
  width: 10px;
  height: 10px;
  border: 0;
  border-radius: 2px;
  background: var(--legend-colour);
}

.hpc-programme .legend-item.keynote  { --legend-colour: var(--p-keynote); }
.hpc-programme .legend-item.tutorial { --legend-colour: var(--p-tutorial); }
.hpc-programme .legend-item.talk     { --legend-colour: var(--p-talk); }
.hpc-programme .legend-item.workshop { --legend-colour: var(--p-workshop); }
.hpc-programme .legend-item.meeting  { --legend-colour: var(--p-meeting); }
.hpc-programme .legend-item.social   { --legend-colour: var(--p-social); }
.hpc-programme .legend-item.poster   { --legend-colour: var(--p-other); }

.hpc-programme .legend-item.active {
  color: #fff;
  background: var(--purple);
  border-color: var(--purple-light);
}

.hpc-programme .legend-item.active .legend-colour {
  box-shadow: 0 0 0 3px rgba(255,255,255,.12);
}

.hpc-programme .programme-filter-status {
  min-height: 20px;
  margin: 8px 0 14px;
  color: var(--muted);
  font-size: 13px;
}

/* Horizontal timetable viewport */
.hpc-programme .programme-scroll {
  max-width: 100%;
  overflow-x: auto;
  overscroll-behaviour-x: contain;
  border: 1px solid var(--line);
  background: var(--bg);
  scrollbar-color: var(--purple-light) var(--card);
  scrollbar-width: thin;
}

.hpc-programme .programme-scroll:focus-visible {
  outline: 3px solid var(--purple-light);
  outline-offset: 4px;
}

.hpc-programme .week-grid {
  display: grid;
  gap: 6px;
  min-width: calc(var(--programme-time-width) + 5 * var(--programme-day-width) + 6 * var(--programme-gap));
  padding: 8px;
}

/* Day headers */
.hpc-programme .week-header,
.hpc-programme .week-row {
  display: grid;
  grid-template-columns: var(--programme-time-width) repeat(5, minmax(var(--programme-day-width), 1fr));
  gap: var(--programme-gap);
  align-items: stretch;
}

.hpc-programme .week-header {
  position: sticky;
  top: 0;
  z-index: 10;
}

.hpc-programme .week-time-header,
.hpc-programme .week-day-header {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  min-height: 68px;
  padding: 12px 14px;
  text-align: left;
  color: #fff;
  background: #2A0E2E;
  border: 1px solid rgba(255,255,255,.1);
  border-top: 3px solid var(--purple-light);
  border-radius: 4px;
  font-size: 14px;
  font-weight: 800;
}

.hpc-programme .week-time-header {
  align-items: center;
  background: var(--card);
  border-top-color: var(--line);
}

.hpc-programme .day-name {
  font-size: 16px;
  line-height: 1.25;
}

.hpc-programme .day-date {
  margin-top: 5px;
  color: var(--purple-soft);
  font-size: 12px;
  font-weight: 600;
}

/* Time column */
.hpc-programme .week-time {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding: 15px 4px;
  color: var(--muted);
  background: var(--alt);
  border: 1px solid var(--line);
  border-radius: 4px;
  font-size: 13px;
  font-weight: 800;
  font-variant-numeric: tabular-nums;
}

/* Cells */
.hpc-programme .week-cell {
  display: flex;
  flex-direction: column;
  gap: 7px;
  min-width: 0;
  min-height: 64px;
  height: 100%;
  padding: 6px;
  background: var(--alt);
  border: 1px solid var(--programme-keyline);
  border-radius: 4px;
}

.hpc-programme .empty-cell {
  flex: 1;
  min-height: 48px;
  background:
    radial-gradient(rgba(255,255,255,.06) 1px, transparent 1px) 0 0 / 12px 12px;
  border-radius: 2px;
}

.hpc-programme .week-row {
  min-height: 82px;
}

/* Session cards */
.hpc-programme .session-card {
  --session-colour: var(--purple-light);
  display: flex;
  flex-direction: column;
  flex: 1 0 auto;
  min-width: 0;
  margin: 0;
  padding: 12px;
  color: var(--text);
  background: var(--card);
  border: 1px solid var(--line);
  border-top: 3px solid var(--session-colour);
  border-radius: 4px;
  overflow-wrap: anywhere;
  transition: background .2s ease, border-color .2s ease, transform .2s ease, opacity .2s ease;
}

.hpc-programme .session-card.keynote  { --session-colour: var(--p-keynote); }
.hpc-programme .session-card.tutorial { --session-colour: var(--p-tutorial); }
.hpc-programme .session-card.talk     { --session-colour: var(--p-talk); }
.hpc-programme .session-card.workshop { --session-colour: var(--p-workshop); }
.hpc-programme .session-card.meeting  { --session-colour: var(--p-meeting); }
.hpc-programme .session-card.social   { --session-colour: var(--p-social); }
.hpc-programme .session-card.poster,
.hpc-programme .session-card.other    { --session-colour: var(--p-other); }

.hpc-programme .session-card:hover {
  background: var(--session-colour);
  border-color: var(--session-colour);
  transform: translateY(-2px);
  box-shadow: 0 8px 18px rgba(0,0,0,.25);
  filter: none;
  cursor: default;
}

.hpc-programme .session-header {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 7px;
}

.hpc-programme .session-category {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  color: var(--session-colour);
  font-size: 10px;
  font-weight: 800;
  letter-spacing: .09em;
  line-height: 1.3;
  text-transform: uppercase;
}

.hpc-programme .session-title {
  margin: 0;
  font-size: 15px;
  font-weight: 800;
  line-height: 1.3;
}

.hpc-programme .session-card .session-title a {
  color: var(--text) !important;
  text-decoration: none;
  text-underline-offset: 3px;
}

.hpc-programme .session-card .session-title a:hover {
  color: var(--text) !important;
  text-decoration: underline;
}

.hpc-programme .session-card:hover .session-title a,
.hpc-programme .session-card:hover .meta-line,
.hpc-programme .session-card:hover .meta-label,
.hpc-programme .session-card:hover .hybrid-link {
  color: var(--ink) !important;
}

.hpc-programme .session-card:hover .session-category {
  color: var(--ink);
}

.hpc-programme .session-meta {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 5px;
  margin-top: 5px;
  color: var(--muted);
}

.hpc-programme .meta-line {
  display: flex;
  align-items: baseline;
  gap: 5px;
  margin: 0;
  font-size: 12px;
  line-height: 1.35;
}

.hpc-programme .meta-label {
  flex-shrink: 0;
  color: #E3D5E9;
  font-size: 11px;
  font-weight: 800;
}

.hpc-programme .meta-line.room {
  color: var(--muted);
  font-weight: 700;
}

.hpc-programme .hybrid-link {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  margin-top: 4px;
  padding: 4px 7px;
  color: #BDE9FF;
  background: rgba(91,180,229,.1);
  border: 1px solid rgba(91,180,229,.25);
  border-radius: 3px;
  font-size: 11px;
  font-weight: 700;
}

/* Fixed breaks and lunch */
.hpc-programme .fixed-session {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 10px;
  min-height: 54px;
  padding: 12px;
  color: var(--muted);
  background: #18101D;
  border: 1px dashed #65446D;
  border-radius: 4px;
  font-size: 14px;
  font-weight: 800;
  letter-spacing: .04em;
  text-transform: uppercase;
}

.hpc-programme .fixed-icon {
  color: var(--purple-light);
  font-size: 19px;
}

/* Category highlighting */
.hpc-programme .session-card.dimmed {
  opacity: .18;
  transform: none;
}

.hpc-programme .session-card.highlighted {
  opacity: 1;
  border-color: var(--session-colour);
  box-shadow: 0 0 0 1px var(--session-colour), 0 8px 20px rgba(0,0,0,.3);
  transform: translateY(-2px);
  z-index: 2;
}

.hpc-programme .session-card.highlighted:hover {
  background: var(--session-colour);
}

.hpc-programme .session-card.highlighted:hover .session-title a,
.hpc-programme .session-card.highlighted:hover .session-category,
.hpc-programme .session-card.highlighted:hover .meta-line,
.hpc-programme .session-card.highlighted:hover .meta-label {
  color: var(--ink) !important;
}

/* Below timetable */
.hpc-programme .programme-scroll-note {
  margin: 10px 0 0;
  color: var(--muted);
  font-size: 12px;
}

.hpc-programme .programme-footer {
  display: flex;
  align-items: flex-start;
  gap: 14px;
  margin-top: 32px;
  padding: 22px 24px;
  background: var(--card);
  border: 1px solid var(--line);
  border-left: 4px solid var(--purple-light);
}

.hpc-programme .programme-footer-mark {
  color: var(--purple-light);
  font-size: 23px;
  line-height: 1.2;
}

.hpc-programme .programme-footer p {
  margin: 0;
  color: var(--muted);
  font-size: 15px;
}

.hpc-programme .programme-footer a {
  font-weight: 700;
}

/* Responsive adjustments */
@media (max-width: 1100px) {
  .hpc-programme .programme-intro {
    align-items: flex-start;
    flex-direction: column;
  }

  .hpc-programme .programme-links {
    padding-bottom: 0;
  }
}

@media (max-width: 680px) {
  .hpc-programme .hpc-pagehead {
    padding: 38px 0 42px;
  }

  .hpc-programme .hpc-crumbs {
    margin-bottom: 18px;
    font-size: 13px;
  }

  .hpc-programme .hpc-facts {
    gap: 16px 24px;
  }

  .hpc-programme .hpc-actions {
    align-items: stretch;
    flex-direction: column;
  }

  .hpc-programme .hpc-actions .hpc-btn {
    text-align: center;
  }

  .hpc-programme-section {
    padding: 36px 0 46px;
  }

  .hpc-programme .programme-links {
    flex-direction: column;
    gap: 8px;
  }

  .hpc-programme .programme-legend {
    gap: 6px;
  }

  .hpc-programme .legend-item {
    min-height: 35px;
    padding: 6px 10px;
    font-size: 12px;
  }

  .hpc-programme .programme-scroll {
    margin-right: -4px;
  }

  .hpc-programme .programme-footer {
    padding: 18px;
  }
}

/* Respect reduced-motion preferences */
@media (prefers-reduced-motion: reduce) {
  .hpc-programme *,
  .hpc-programme *::before,
  .hpc-programme *::after {
    transition: none !important;
    animation: none !important;
    scroll-behavior: auto !important;
  }
}


/* Personal timetable toolbar */
.hpc-programme .my-timetable-toolbar {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  margin: 1.5rem 0;
  padding: 1.1rem 1.25rem;
  background: var(--card);
  border: 1px solid var(--line);
  border-radius: 14px;
}

.hpc-programme .my-timetable-intro {
  display: grid;
  gap: 0.2rem;
}

.hpc-programme .my-timetable-intro strong {
  color: var(--text);
  font-size: 1.05rem;
}

.hpc-programme #my-timetable-count {
  color: var(--muted);
  font-size: 0.9rem;
}

.hpc-programme .my-timetable-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.hpc-programme .my-timetable-actions .hpc-btn {
  cursor: pointer;
}

.hpc-programme #my-timetable-status {
  flex-basis: 100%;
  margin: 0;
  color: var(--purple-light);
  font-size: 0.9rem;
}

.hpc-programme .session-save {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  margin-top: 0.65rem;
  padding: 0.4rem 0.7rem;
  border: 1px solid var(--purple-light);
  border-radius: 7px;
  background: transparent;
  color: var(--text);
  font: inherit;
  font-size: 0.82rem;
  font-weight: 600;
  cursor: pointer;
}

.hpc-programme .session-save:hover,
.hpc-programme .session-save[aria-pressed="true"] {
  background: var(--purple);
  border-color: var(--purple-light);
  color: #fff;
}

.hpc-programme .session-card.is-selected {
  box-shadow: 0 0 0 1px var(--purple-light);
}

.hpc-programme .week-row[hidden],
.hpc-programme .session-card[hidden] {
  display: none !important;
}

@media print {
  body * {
    visibility: hidden;
  }

  .hpc-programme,
  .hpc-programme .programme-scroll,
  .hpc-programme .week-grid,
  .hpc-programme .week-grid * {
    visibility: visible;
  }

  .hpc-programme .my-timetable-toolbar,
  .hpc-programme .session-save,
  .hpc-programme .legend,
  .hpc-programme .programme-actions {
    display: none !important;
  }

  .hpc-programme .programme-scroll {
    overflow: visible !important;
  }

  .hpc-programme .week-grid {
    min-width: 0 !important;
  }

  .hpc-programme .session-card {
    break-inside: avoid;
    box-shadow: none !important;
  }

  .hpc-programme.personal-view .week-row[hidden],
  .hpc-programme.personal-view .session-card[hidden] {
    display: none !important;
  }
}
</style>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const root = document.querySelector(".hpc-programme");
  if (!root) return;

  const legendItems = root.querySelectorAll(".legend-item");
  const sessions = root.querySelectorAll(".session-card");
  const status = root.querySelector(".programme-filter-status");

  let activeCategory = null;

  function resetHighlight() {
    sessions.forEach(session => {
      session.classList.remove("highlighted", "dimmed");
    });

    legendItems.forEach(item => {
      item.classList.remove("active");
      item.setAttribute("aria-pressed", "false");
    });

    activeCategory = null;

    if (status) status.textContent = "Showing all session types.";
  }

  function highlightCategory(category, selectedItem) {
    sessions.forEach(session => {
      const matches =
        session.dataset.sessionCategory === category;

      session.classList.toggle("highlighted", matches);
      session.classList.toggle("dimmed", !matches);
    });

    legendItems.forEach(item => {
      const active = item === selectedItem;
      item.classList.toggle("active", active);
      item.setAttribute("aria-pressed", String(active));
    });

    activeCategory = category;

    const label = selectedItem.textContent.trim();

    if (status) {
      status.textContent = "Highlighting: " + label + ". Select again or click elsewhere to reset.";
    }
  }

  legendItems.forEach(item => {
    const category = item.dataset.category;

    item.addEventListener("mouseenter", () => {
      if (!activeCategory) {
        sessions.forEach(session => {
          const matches =
            session.dataset.sessionCategory === category;

          session.classList.toggle("highlighted", matches);
          session.classList.toggle("dimmed", !matches);
        });
      }
    });

    item.addEventListener("mouseleave", () => {
      if (!activeCategory) resetHighlight();
    });

    item.addEventListener("focus", () => {
      if (!activeCategory) {
        sessions.forEach(session => {
          const matches =
            session.dataset.sessionCategory === category;

          session.classList.toggle("highlighted", matches);
          session.classList.toggle("dimmed", !matches);
        });
      }
    });

    item.addEventListener("blur", () => {
      if (!activeCategory) resetHighlight();
    });

    item.addEventListener("click", () => {
      if (activeCategory === category) {
        resetHighlight();
      } else {
        highlightCategory(category, item);
      }
    });

    item.addEventListener("keydown", event => {
      if (event.key === "Escape") resetHighlight();
    });
  });

  root.addEventListener("click", event => {
    if (!activeCategory) return;

    if (!event.target.closest(".legend-item")) {
      resetHighlight();
    }
  });
});
</script>
<script>
document.addEventListener("DOMContentLoaded", () => {
  const root = document.querySelector(".hpc-programme");
  if (!root) return;

  const storageKey = "durham-hpc-days-2026-my-timetable";
  const cards = [...root.querySelectorAll(".session-card")];
  const count = document.getElementById("my-timetable-count");
  const status = document.getElementById("my-timetable-status");
  const toggle = document.getElementById("toggle-my-timetable");
  const print = document.getElementById("print-my-timetable");
  const clear = document.getElementById("clear-my-timetable");

  let selected = new Set();
  let personalView = false;

  try {
    selected = new Set(
      JSON.parse(localStorage.getItem(storageKey) || "[]")
    );
  } catch {
    selected = new Set();
  }

  // Ensure every session has a stable ID.
  cards.forEach((card, index) => {
    if (!card.dataset.sessionId) {
      card.dataset.sessionId =
        card.querySelector(".session-title a")?.getAttribute("href")
        || `session-${index}`;
    }

    const id = card.dataset.sessionId;
    const button = document.createElement("button");
    button.type = "button";
    button.className = "session-save";
    button.dataset.sessionId = id;
    button.addEventListener("click", () => {
      if (selected.has(id)) {
        selected.delete(id);
        status.textContent = "Session removed from your timetable.";
      } else {
        selected.add(id);
        status.textContent = "Session added to your timetable.";
        warnAboutClashes(card);
      }

      save();
      render();
    });

    card.append(button);
  });

  function save() {
    try {
      localStorage.setItem(storageKey, JSON.stringify([...selected]));
    } catch {
      status.textContent =
        "Your browser could not save your timetable. Check its storage settings.";
    }
  }

  function warnAboutClashes(addedCard) {
    const start = Date.parse(addedCard.dataset.start);
    const end = Date.parse(addedCard.dataset.end);

    if (!Number.isFinite(start) || !Number.isFinite(end)) return;

    const clashes = cards.filter(card => {
      if (card === addedCard || !selected.has(card.dataset.sessionId)) {
        return false;
      }

      const otherStart = Date.parse(card.dataset.start);
      const otherEnd = Date.parse(card.dataset.end);

      return Number.isFinite(otherStart) &&
        Number.isFinite(otherEnd) &&
        start < otherEnd &&
        end > otherStart;
    });

    if (clashes.length) {
      const names = clashes.map(card =>
        card.querySelector(".session-title")?.innerText.trim()
        || "another session"
      );

      status.textContent =
        "Potential time clash with: " + names.join(", ") + ".";
    }
  }

  function render() {
    let visibleCount = 0;

    cards.forEach(card => {
      const isSelected = selected.has(card.dataset.sessionId);
      const button = card.querySelector(".session-save");

      button.textContent = isSelected ? "✓ Added" : "+ Add";
      button.setAttribute("aria-pressed", String(isSelected));
      button.setAttribute(
        "aria-label",
        `${isSelected ? "Remove" : "Add"} ${
          card.querySelector(".session-title")?.innerText.trim()
          || "session"
        } ${isSelected ? "from" : "to"} your timetable`
      );

      card.classList.toggle("is-selected", isSelected);
      card.classList.toggle("is-not-selected", personalView && !isSelected);

      if (personalView && !isSelected) {
        card.hidden = true;
      } else {
        card.hidden = false;
        visibleCount++;
      }
    });

    // Hide timetable rows that contain no remaining sessions
    // when the personal view is active.
    root.querySelectorAll(".week-row").forEach(row => {
      const rowCards = [...row.querySelectorAll(".session-card")];
      row.hidden = personalView &&
        rowCards.length > 0 &&
        !rowCards.some(card => selected.has(card.dataset.sessionId));
    });

    count.textContent =
      `${selected.size} session${selected.size === 1 ? "" : "s"} selected`;

    toggle.textContent = personalView
      ? "View full programme"
      : "View my timetable";

    root.classList.toggle("personal-view", personalView);
  }

  toggle.addEventListener("click", () => {
    personalView = !personalView;
    render();

    if (personalView && selected.size === 0) {
      status.textContent =
        "You haven't added any sessions yet. Select + Add on a session.";
    } else {
      status.textContent = personalView
        ? "Showing your selected sessions."
        : "Showing the full programme.";
    }
  });

  clear.addEventListener("click", () => {
    if (!selected.size) {
      status.textContent = "Your timetable is already empty.";
      return;
    }

    if (!confirm("Clear all sessions from your personal timetable?")) return;

    selected.clear();
    save();
    render();
    status.textContent = "All selections cleared.";
  });

  print.addEventListener("click", () => {
    if (!selected.size) {
      status.textContent = "Add at least one session before printing.";
      return;
    }

  });

  render();
});
</script>