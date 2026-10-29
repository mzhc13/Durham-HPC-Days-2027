---
layout: splash
title: "Conference Programme – Week View"
permalink: /programme-week-2027/
classes: [full-programme]
---

{% assign all_sessions = site.programme-days-2027
  | where_exp: "s", "s.start_time"
  | sort: "start_time" %}

{% assign days_order = "Monday 15 June,Tuesday 16 June,Wednesday 17 June,Thursday 18 June,Friday 19 June" | split: "," %}

{% comment %}
  A session can run more than once. The main slot is day / start_time / end_time / room,
  and any repeats live in additional_slots inside the same .md file.
  Collect every start time (main + repeats) so each one gets a row.
{% endcomment %}
{% assign sessions_by_track = all_sessions | sort: "track" %}
{% assign time_slots = all_sessions | map: "start_time" %}
{% for s in all_sessions %}
  {% for slot in s.additional_slots %}
    {% if slot.start_time %}{% assign time_slots = time_slots | push: slot.start_time %}{% endif %}
  {% endfor %}
{% endfor %}
{% assign time_slots = time_slots | uniq | sort %}

{% assign fixed_sessions = "10:30|Coffee Break,12:00|Lunch,14:30|Break,16:00|Coffee Break" | split: "," %}

{% for fs in fixed_sessions %}
  {% assign fs_parts = fs | split: "|" %}
  {% unless time_slots contains fs_parts[0] %}
    {% assign time_slots = time_slots | push: fs_parts[0] %}
  {% endunless %}
{% endfor %}

{% assign time_slots = time_slots | sort %}

<link rel="stylesheet" href="{{ '/assets/css/hpc-days.css' | relative_url }}">

<div class="hpc hpc-programme" data-focus="all">

  <section class="hpc-section hpc-programme-section">
    <div class="hpc-in">

      <div class="programme-intro">
        <div>
          <p class="programme-eyebrow">Plan your week</p>
          <h2>Week at a glance</h2>
          <p class="hpc-sub">
            Pick a day, filter by session type or search for a talk, person or room.
            Use the + on any session to build your own timetable. It is saved in this browser.
          </p>
        </div>

        <div class="programme-links">
          <a href="{{ '/rooms/' | relative_url }}">🗺️ Room map</a>
          <a href="https://raw.githubusercontent.com/hpc-days/Durham-HPC-Days-2026/main/assets/images/booklet-hpcdays-26.pdf">📖 Full booklet</a>
          <a href="https://raw.githubusercontent.com/hpc-days/Durham-HPC-Days-2026/main/assets/images/summary-booklet-hpcdays-26.pdf">📄 Quick overview</a>
        </div>
      </div>

      <!-- DAY TABS + SEARCH -->
      <div class="programme-controls">
        <div class="day-tabs" role="group" aria-label="Choose a day">
          <button type="button" class="day-tab day-all" data-day="all" aria-pressed="true">Whole week</button>
          {% for day in days_order %}
            {% assign p = day | split: " " %}
            <button type="button" class="day-tab" data-day="{{ p[0] }}" aria-pressed="false">
              <span class="tab-long">{{ p[0] }}</span><span class="tab-short">{{ p[0] | slice: 0, 3 }}</span>
              <span class="tab-num">{{ p[1] }}</span>
            </button>
          {% endfor %}
        </div>

        <label class="programme-search">
          <span class="sr-only">Search sessions</span>
          <input type="search" id="programme-search" placeholder="Search title, person or room" autocomplete="off">
        </label>
      </div>

      <!-- SESSION TYPE FILTERS (select several) -->
      <div class="programme-legend" role="group" aria-label="Filter sessions by type">
        <button class="legend-item keynote" type="button" data-category="keynote" aria-pressed="false"><span class="legend-colour"></span> Keynotes <span class="legend-count"></span></button>
        <button class="legend-item tutorial" type="button" data-category="tutorial" aria-pressed="false"><span class="legend-colour"></span> Tutorials <span class="legend-count"></span></button>
        <button class="legend-item talk" type="button" data-category="talk" aria-pressed="false"><span class="legend-colour"></span> Talks <span class="legend-count"></span></button>
        <button class="legend-item workshop" type="button" data-category="workshop" aria-pressed="false"><span class="legend-colour"></span> Workshops <span class="legend-count"></span></button>
        <button class="legend-item meeting" type="button" data-category="meeting" aria-pressed="false"><span class="legend-colour"></span> Meetings <span class="legend-count"></span></button>
        <button class="legend-item social" type="button" data-category="social" aria-pressed="false"><span class="legend-colour"></span> Socials <span class="legend-count"></span></button>
        <button class="legend-item other" type="button" data-category="other" aria-pressed="false"><span class="legend-colour"></span> Other <span class="legend-count"></span></button>
      </div>

      <p class="programme-filter-status" role="status" aria-live="polite">
        <span id="filter-text">Showing all sessions.</span>
        <button type="button" id="clear-filters" class="link-btn" hidden>Clear filters</button>
      </p>

      <!-- MY TIMETABLE -->
      <div class="my-timetable-toolbar">
        <div class="my-timetable-intro">
          <strong id="my-timetable-count">Your timetable is empty</strong>
          <span id="my-timetable-hint">Select + on a session to add it.</span>
        </div>
        <div class="my-timetable-actions">
          <button type="button" id="toggle-my-timetable" class="hpc-btn hpc-btn-sm" aria-pressed="false">Show only my sessions</button>
          <button type="button" id="export-my-timetable" class="hpc-btn hpc-btn-ghost">Add to calendar</button>
          <button type="button" id="print-my-timetable" class="hpc-btn hpc-btn-ghost">Print</button>
          <button type="button" id="clear-my-timetable" class="hpc-btn hpc-btn-ghost">Clear</button>
        </div>
        <p id="my-timetable-status" role="status" aria-live="polite"></p>
      </div>

      <div class="programme-scroll" role="region" aria-label="Weekly programme timetable">
        <div class="week-grid">

          <div class="week-header week-row">
            <div class="week-time-header">Time</div>
            {% for day in days_order %}
              {% assign p = day | split: " " %}
              <div class="week-day-header col" data-day="{{ p[0] }}">
                <span class="day-name">{{ p[0] }}</span>
                <span class="day-date">{{ p[1] }} {{ p[2] }}</span>
              </div>
            {% endfor %}
          </div>

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

            {% assign has_content = true %}

            {% if has_content or is_fixed %}
              <div class="week-row{% if is_fixed %} is-fixed{% endif %}">

                <div class="week-time"><span>{{ time | split: "-" | first }}</span></div>

                {% if is_fixed %}
                  <div class="week-cell fixed-session">
                    <span class="fixed-icon" aria-hidden="true">{% if fixed_title == "Lunch" %}🍽{% else %}◷{% endif %}</span>
                    <span>{{ fixed_title }}</span>
                  </div>

                {% else %}

                  {% for day in days_order %}
                    {% assign day_name = day | split: " " | first %}

                    <div class="week-cell col" data-day="{{ day_name }}">
                      {% capture cell_html %}
                        {% for s in sessions_by_track %}
                          {% assign extra_n = s.additional_slots | size %}
                          {% assign base_id = s.url | default: s.title | slugify %}

                          {% comment %} i = 0 is the main slot (day / start_time / end_time / room); i >= 1 are additional_slots {% endcomment %}
                          {% for i in (0..extra_n) %}
                            {% if i == 0 %}
                              {% assign o_day = s.day %}
                              {% assign o_start = s.start_time %}
                              {% assign o_end = s.end_time %}
                              {% assign o_room = s.room %}
                              {% assign o_id = base_id %}
                            {% else %}
                              {% assign idx = i | minus: 1 %}
                              {% assign slot = s.additional_slots[idx] %}
                              {% assign o_day = slot.day | default: s.day %}
                              {% assign o_start = slot.start_time %}
                              {% assign o_end = slot.end_time %}
                              {% assign o_room = slot.room | default: s.room %}
                              {% assign o_id = base_id | append: "~" | append: i %}
                            {% endif %}

                            {% if o_day == day_name and o_start == time %}
                              {% assign category = s.category | downcase | strip %}
                              {% if category == "" or category == "poster" %}{% assign category = "other" %}{% endif %}

                              <article class="session-card {{ category }}"
                                       data-session-category="{{ category }}"
                                       data-session-id="{{ o_id }}"
                                       data-day="{{ day_name }}"
                                       data-start="{{ o_start }}"
                                       data-end="{{ o_end }}"
                                       data-room="{{ o_room | escape }}"
                                       data-search="{{ s.title | append: ' ' | append: o_room | append: ' ' | append: s.lead | append: ' ' | append: s.instructor | append: ' ' | append: s.facilitator | append: ' ' | append: s.speaker | append: ' ' | append: s.contributor | downcase | escape }}">

                                <div class="session-header">
                                  <div class="session-topline">
                                    <span class="session-category">{% if category == "other" %}Other{% else %}{{ category | capitalize }}{% endif %}</span>
                                    <span class="session-live">Happening now</span>
                                  </div>

                                  <h3 class="session-title"><a href="{{ s.url | relative_url }}">{{ s.title }}</a></h3>

                                  <div class="session-meta">
                                    {% if o_room != blank %}<div class="meta-line room"><span>{{ o_room }}</span></div>{% endif %}
                                    {% if s.lead != blank %}<div class="meta-line"><span class="meta-label">Lead</span><span>{{ s.lead }}</span></div>{% endif %}
                                    {% if s.instructor != blank %}<div class="meta-line"><span class="meta-label">Instructor</span><span>{{ s.instructor }}</span></div>{% endif %}
                                    {% if s.facilitator != blank %}<div class="meta-line"><span class="meta-label">Facilitator</span><span>{{ s.facilitator }}</span></div>{% endif %}
                                    {% if s.speaker != blank and category == "keynote" %}<div class="meta-line"><span class="meta-label">Speaker</span><span>{{ s.speaker }}</span></div>{% endif %}
                                    {% if s.hybrid != blank %}<span class="hybrid-link"><span aria-hidden="true">↗</span> Available online</span>{% endif %}
                                  </div>

                                  <div class="session-clash" hidden></div>
                                </div>

                                <button type="button" class="session-save" aria-pressed="false"></button>
                              </article>
                            {% endif %}
                          {% endfor %}
                        {% endfor %}
                      {% endcapture %}

                      {% if cell_html contains "<article" %}{{ cell_html }}{% else %}<div class="empty-cell" aria-hidden="true"></div>{% endif %}
                    </div>
                  {% endfor %}

                {% endif %}
              </div>
            {% endif %}
          {% endfor %}

        </div>
      </div>

      <div class="programme-footer">
        <span class="programme-footer-mark" aria-hidden="true">✳</span>
        <p>
          Need more detail? Check the
          <a href="https://raw.githubusercontent.com/hpc-days/Durham-HPC-Days-2026/main/assets/images/booklet-hpcdays-26.pdf">full programme booklet</a>
          or use the <a href="{{ '/rooms/' | relative_url }}">room map</a> to plan your journey between sessions.
        </p>
      </div>

    </div>
  </section>
</div>

<style>
/* ==========================================================================
   DURHAM HPC DAYS 2026: WEEKLY PROGRAMME
   Uses the shared .hpc design tokens. All styles are page-scoped.
   ========================================================================== */

.hpc-programme {
  --programme-time-width: 76px;
  --programme-gap: 10px;
  --programme-keyline: rgba(255,255,255,.08);
  --sticky-top: 0px;               /* set to your navbar height if it is sticky */
  --cols: 5;

  --p-keynote: var(--s-keynote);
  --p-tutorial: var(--s-tutorial);
  --p-talk: var(--s-talk);
  --p-workshop: var(--s-workshop);
  --p-meeting: var(--s-meeting);
  --p-social: var(--s-social);
  --p-other: #C2A8F5;

  background: var(--bg);
  color: var(--text);
}
.hpc-programme .hpc-in { width: min(98%, 1800px); max-width: 1800px; margin-inline: auto; }
.hpc-programme [hidden] { display: none !important; }
.hpc-programme .sr-only { position: absolute; width: 1px; height: 1px; overflow: hidden; clip: rect(0 0 0 0); white-space: nowrap; }
.hpc-programme .hpc-btn { font-family: inherit; }
.hpc-programme .hpc-btn:disabled { opacity: .4; cursor: not-allowed; transform: none; }

.hpc-programme-section { padding: 46px 0 64px; }

/* Intro */
.hpc-programme .programme-intro { display: flex; align-items: flex-end; justify-content: space-between; gap: 24px; margin-bottom: 26px; }
.hpc-programme .programme-intro h2 { margin-bottom: 10px; border-bottom: 0 !important; }
.hpc-programme .programme-intro .hpc-sub { max-width: 650px; margin-bottom: 0 !important; }
.hpc-programme .programme-eyebrow { margin-bottom: 8px; color: var(--purple-light); font-size: 13px; font-weight: 800; letter-spacing: .12em; text-transform: uppercase; }
.hpc-programme .programme-links { display: flex; flex-wrap: wrap; gap: 8px 18px; padding-bottom: 4px; }
.hpc-programme .programme-links a { font-size: 14px; font-weight: 700; text-decoration: none; white-space: nowrap; }
.hpc-programme .programme-links a:hover { text-decoration: underline; }

/* Day tabs and search */
.hpc-programme .programme-controls { display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: 12px 24px; margin-bottom: 14px; }
.hpc-programme .day-tabs { display: flex; flex-wrap: wrap; gap: 6px; }
.hpc-programme .day-tab {
  padding: 9px 16px; color: var(--muted); background: var(--card);
  border: 1px solid var(--line); border-radius: 5px;
  font: inherit; font-size: 14px; font-weight: 700; cursor: pointer;
  transition: background .2s, color .2s, border-color .2s;
}
.hpc-programme .day-tab:hover { color: #fff; border-color: var(--purple-light); }
.hpc-programme .day-tab[aria-pressed="true"] { color: #fff; background: var(--purple); border-color: var(--purple-light); }
.hpc-programme .tab-num { margin-left: 4px; font-weight: 600; opacity: .7; }
.hpc-programme .tab-short { display: none; }

.hpc-programme .programme-search input {
  width: min(100%, 340px); padding: 9px 14px; color: var(--text); background: var(--card);
  border: 1px solid var(--line); border-radius: 5px; font: inherit; font-size: 14px;
}
.hpc-programme .programme-search input::placeholder { color: var(--muted); }
.hpc-programme .programme-search input:focus { outline: none; border-color: var(--purple-light); box-shadow: 0 0 0 3px rgba(201,138,207,.25); }

/* Type filters */
.hpc-programme .programme-legend { display: flex; flex-wrap: wrap; gap: 8px; margin: 0 0 8px; }
.hpc-programme .legend-item {
  display: inline-flex; align-items: center; gap: 9px; min-height: 38px; padding: 7px 13px;
  color: var(--muted); background: var(--card); border: 1px solid var(--line); border-radius: 5px;
  font: inherit; font-size: 13px; font-weight: 700; cursor: pointer;
  transition: background .2s, color .2s, border-color .2s;
}
.hpc-programme .legend-item:hover { color: #fff; border-color: var(--purple-light); }
.hpc-programme .legend-colour { width: 10px; height: 10px; border-radius: 2px; background: var(--legend-colour); }
.hpc-programme .legend-count { font-weight: 600; opacity: .65; }
.hpc-programme .legend-item.keynote  { --legend-colour: var(--p-keynote); }
.hpc-programme .legend-item.tutorial { --legend-colour: var(--p-tutorial); }
.hpc-programme .legend-item.talk     { --legend-colour: var(--p-talk); }
.hpc-programme .legend-item.workshop { --legend-colour: var(--p-workshop); }
.hpc-programme .legend-item.meeting  { --legend-colour: var(--p-meeting); }
.hpc-programme .legend-item.social   { --legend-colour: var(--p-social); }
.hpc-programme .legend-item.other    { --legend-colour: var(--p-other); }
.hpc-programme .legend-item[aria-pressed="true"] { color: #fff; background: var(--purple); border-color: var(--purple-light); }
.hpc-programme .legend-item[aria-pressed="true"] .legend-colour { box-shadow: 0 0 0 3px rgba(255,255,255,.14); }

.hpc-programme .programme-filter-status { min-height: 22px; margin: 8px 0 14px; color: var(--muted); font-size: 13px; }
.hpc-programme .link-btn { margin-left: 10px; padding: 0; color: var(--purple-light); background: none; border: 0; font: inherit; font-weight: 700; text-decoration: underline; text-underline-offset: 3px; cursor: pointer; }

/* My timetable */
.hpc-programme .my-timetable-toolbar {
  display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: 1rem;
  margin: 0 0 1.25rem; padding: 1.1rem 1.25rem; background: var(--card); border: 1px solid var(--line); border-radius: 14px;
}
.hpc-programme .my-timetable-intro { display: grid; gap: .2rem; }
.hpc-programme .my-timetable-intro strong { color: var(--text); font-size: 1.05rem; }
.hpc-programme #my-timetable-hint { color: var(--muted); font-size: .9rem; }
.hpc-programme .my-timetable-actions { display: flex; flex-wrap: wrap; gap: .5rem; }
.hpc-programme #my-timetable-status { flex-basis: 100%; min-height: 0; margin: 0; color: var(--purple-light); font-size: .9rem; }
.hpc-programme #my-timetable-status:empty { display: none; }

/* Timetable */
.hpc-programme .programme-scroll { border: 1px solid var(--line); background: var(--bg); }
.hpc-programme .week-grid { display: grid; gap: 6px; padding: 8px; }

.hpc-programme .week-row {
  display: grid;
  grid-template-columns: var(--programme-time-width) repeat(var(--cols), minmax(0, 1fr));
  gap: var(--programme-gap);
  align-items: stretch;
  min-height: 82px;
}
.hpc-programme .week-header { position: sticky; top: var(--sticky-top); z-index: 10; min-height: 0; padding: 2px 0 6px; background: var(--bg); }

.hpc-programme .week-time-header,
.hpc-programme .week-day-header {
  display: flex; flex-direction: column; align-items: flex-start; justify-content: center;
  min-height: 68px; padding: 12px 14px; color: #fff; background: #2A0E2E;
  border: 1px solid rgba(255,255,255,.1); border-top: 3px solid var(--purple-light); border-radius: 4px;
  font-size: 14px; font-weight: 800;
}
.hpc-programme .week-time-header { align-items: center; background: var(--card); border-top-color: var(--line); }
.hpc-programme .day-name { font-size: 16px; line-height: 1.25; }
.hpc-programme .day-date { margin-top: 5px; color: var(--purple-soft); font-size: 12px; font-weight: 600; }

.hpc-programme .week-time {
  display: flex; justify-content: center; align-items: flex-start; padding: 15px 4px;
  color: var(--muted); background: var(--alt); border: 1px solid var(--line); border-radius: 4px;
  font-size: 13px; font-weight: 800; font-variant-numeric: tabular-nums;
}
.hpc-programme .week-cell {
  display: flex; flex-direction: column; gap: 7px; min-width: 0; min-height: 64px; height: 100%; padding: 6px;
  background: var(--alt); border: 1px solid var(--programme-keyline); border-radius: 4px;
}
.hpc-programme .empty-cell { flex: 1; min-height: 48px; background: radial-gradient(rgba(255,255,255,.06) 1px, transparent 1px) 0 0 / 12px 12px; border-radius: 2px; }

/* Session cards */
.hpc-programme .session-card {
  --session-colour: var(--purple-light);
  position: relative; display: flex; flex-direction: column; flex: 1 0 auto; min-width: 0;
  margin: 0; padding: 12px 46px 12px 12px; color: var(--text);
  background: var(--card); border: 1px solid var(--line); border-top: 3px solid var(--session-colour); border-radius: 4px;
  overflow-wrap: anywhere;
  transition: background .2s ease, border-color .2s ease, transform .2s ease, opacity .2s ease;
}
.hpc-programme .session-card.keynote  { --session-colour: var(--p-keynote); }
.hpc-programme .session-card.tutorial { --session-colour: var(--p-tutorial); }
.hpc-programme .session-card.talk     { --session-colour: var(--p-talk); }
.hpc-programme .session-card.workshop { --session-colour: var(--p-workshop); }
.hpc-programme .session-card.meeting  { --session-colour: var(--p-meeting); }
.hpc-programme .session-card.social   { --session-colour: var(--p-social); }
.hpc-programme .session-card.other    { --session-colour: var(--p-other); }

.hpc-programme .session-card:hover { background: var(--session-colour); border-color: var(--session-colour); transform: translateY(-2px); box-shadow: 0 8px 18px rgba(0,0,0,.25); }
.hpc-programme .session-header { display: flex; flex-direction: column; align-items: flex-start; gap: 7px; }
.hpc-programme .session-topline { display: flex; flex-wrap: wrap; align-items: center; gap: 8px; }
.hpc-programme .session-category { color: var(--session-colour); font-size: 10px; font-weight: 800; letter-spacing: .09em; line-height: 1.3; text-transform: uppercase; }
.hpc-programme .session-live { display: none; padding: 1px 7px; color: var(--ink); background: #fff; border-radius: 3px; font-size: 10px; font-weight: 800; }
.hpc-programme .session-card.is-live .session-live { display: inline-block; }

.hpc-programme .session-title { margin: 0; font-size: 15px; font-weight: 800; line-height: 1.3; }
.hpc-programme .session-card .session-title a { color: var(--text) !important; text-decoration: none; text-underline-offset: 3px; }
.hpc-programme .session-card .session-title a:hover { text-decoration: underline; }
.hpc-programme .session-card:hover .session-title a,
.hpc-programme .session-card:hover .meta-line,
.hpc-programme .session-card:hover .meta-label,
.hpc-programme .session-card:hover .hybrid-link,
.hpc-programme .session-card:hover .session-category { color: var(--ink) !important; }

.hpc-programme .session-meta { display: flex; flex-direction: column; align-items: flex-start; gap: 5px; margin-top: 2px; color: var(--muted); }
.hpc-programme .meta-line { display: flex; align-items: baseline; gap: 5px; margin: 0; font-size: 12px; line-height: 1.35; }
.hpc-programme .meta-label { flex-shrink: 0; color: #E3D5E9; font-size: 11px; font-weight: 800; }
.hpc-programme .meta-line.room { color: var(--muted); font-weight: 700; }
.hpc-programme .hybrid-link {
  display: inline-flex; align-items: center; gap: 5px; margin-top: 4px; padding: 4px 7px;
  color: #BDE9FF; background: rgba(91,180,229,.1); border: 1px solid rgba(91,180,229,.25); border-radius: 3px; font-size: 11px; font-weight: 700;
}
.hpc-programme .session-clash { padding: 4px 8px; color: #FFB4A8; background: rgba(255,120,100,.12); border: 1px solid rgba(255,120,100,.4); border-radius: 3px; font-size: 12px; font-weight: 700; }
.hpc-programme .session-card:hover .session-clash { color: #7A1208; background: rgba(255,255,255,.5); border-color: rgba(122,18,8,.4); }

/* Add / remove button */
.hpc-programme .session-save {
  display: none; position: absolute; top: 9px; right: 9px; width: 30px; height: 30px; padding: 0;
  color: var(--session-colour); background: transparent; border: 1.5px solid var(--session-colour); border-radius: 50%;
  font: inherit; font-size: 18px; font-weight: 700; line-height: 1; cursor: pointer;
  transition: background .2s, color .2s, border-color .2s;
}
.hpc-programme.is-ready .session-save { display: block; }
.hpc-programme .session-save:hover { background: rgba(255,255,255,.12); }
.hpc-programme .session-save[aria-pressed="true"] { color: var(--ink); background: var(--session-colour); }
.hpc-programme .session-card:hover .session-save { color: var(--ink); border-color: var(--ink); }
.hpc-programme .session-card:hover .session-save[aria-pressed="true"] { color: var(--session-colour); background: var(--ink); }

.hpc-programme .session-card.is-selected { background: #2B1A38; box-shadow: 0 0 0 1px var(--session-colour); }
.hpc-programme .session-card.is-selected:hover { background: var(--session-colour); }
.hpc-programme .session-card.is-clash { border-color: #FF7864; box-shadow: 0 0 0 1px #FF7864; }
.hpc-programme .session-card.is-dim { opacity: .18; transform: none; }

/* Breaks and lunch */
.hpc-programme .fixed-session {
  grid-column: 2 / -1; flex-direction: row; align-items: center; justify-content: center; gap: 10px;
  min-height: 54px; height: auto; padding: 12px; color: var(--muted); background: #18101D; border: 1px dashed #65446D;
  font-size: 14px; font-weight: 800; letter-spacing: .04em; text-transform: uppercase;
}
.hpc-programme .fixed-icon { color: var(--purple-light); font-size: 19px; }

/* Footer */
.hpc-programme .programme-footer { display: flex; align-items: flex-start; gap: 14px; margin-top: 32px; padding: 22px 24px; background: var(--card); border: 1px solid var(--line); border-left: 4px solid var(--purple-light); }
.hpc-programme .programme-footer-mark { color: var(--purple-light); font-size: 23px; line-height: 1.2; }
.hpc-programme .programme-footer p { margin: 0; color: var(--muted); font-size: 15px; }
.hpc-programme .programme-footer a { font-weight: 700; }

/* Single-day view: wider cards, so slightly larger type */
.hpc-programme:not([data-focus="all"]) .session-title { font-size: 17px; }
.hpc-programme:not([data-focus="all"]) .meta-line { font-size: 13px; }

/* Narrow screens: one day at a time, no sideways scrolling */
@media (max-width: 1100px) {
  .hpc-programme .programme-intro { align-items: flex-start; flex-direction: column; }
  .hpc-programme .programme-links { padding-bottom: 0; }
}
@media (max-width: 1000px) {
  .hpc-programme .day-all { display: none; }
}
@media (max-width: 680px) {
  .hpc-programme-section { padding: 36px 0 46px; }
  .hpc-programme .programme-links { flex-direction: column; gap: 8px; }
  .hpc-programme .day-tabs { width: 100%; flex-wrap: nowrap; }
  .hpc-programme .day-tab { flex: 1; padding: 8px 2px; text-align: center; }
  .hpc-programme .tab-long { display: none; }
  .hpc-programme .tab-short { display: inline; }
  .hpc-programme .tab-num { display: block; margin: 0; font-size: 12px; }
  .hpc-programme .programme-search { width: 100%; }
  .hpc-programme .programme-search input { width: 100%; }
  .hpc-programme .legend-item { min-height: 35px; padding: 6px 10px; font-size: 12px; }
  .hpc-programme .week-row { --programme-time-width: 54px; --programme-gap: 6px; }
  .hpc-programme .week-header { display: none; }
  .hpc-programme .programme-footer { padding: 18px; }
}

@media (prefers-reduced-motion: reduce) {
  .hpc-programme *, .hpc-programme *::before, .hpc-programme *::after { transition: none !important; animation: none !important; scroll-behavior: auto !important; }
}

/* Print: light, ink-friendly timetable (your selection if you have one) */
@media print {
  body * { visibility: hidden; }
  .hpc-programme, .hpc-programme .week-grid, .hpc-programme .week-grid * { visibility: visible; }
  .hpc-programme { position: absolute; left: 0; top: 0; width: 100%; margin: 0; background: #fff; color: #000; -webkit-print-color-adjust: exact; print-color-adjust: exact; }
  .hpc-programme-section { padding: 0; }
  .hpc-programme .programme-intro, .hpc-programme .programme-controls, .hpc-programme .programme-legend,
  .hpc-programme .programme-filter-status, .hpc-programme .my-timetable-toolbar,
  .hpc-programme .programme-footer, .hpc-programme .session-save { display: none !important; }
  .hpc-programme .programme-scroll { border: 0; background: #fff; }
  .hpc-programme .week-header { position: static; background: #fff; }
  .hpc-programme .week-cell, .hpc-programme .week-time, .hpc-programme .fixed-session { background: #fff; border-color: #bbb; color: #000; }
  .hpc-programme .week-day-header, .hpc-programme .week-time-header { color: #000; background: #eee; border-color: #bbb; }
  .hpc-programme .day-date { color: #444; }
  .hpc-programme .session-card { color: #000; background: #fff !important; border-color: #999; box-shadow: none !important; opacity: 1 !important; break-inside: avoid; }
  .hpc-programme .session-card .session-title a, .hpc-programme .meta-line, .hpc-programme .meta-label { color: #000 !important; }
  .hpc-programme .session-category { color: #333 !important; }
  .hpc-programme .empty-cell { background: none; }
}
</style>

<script>
document.addEventListener("DOMContentLoaded", function () {
  var root = document.querySelector(".hpc-programme");
  if (!root) return;

  var DAYS = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"];
  var FIRST_DAY = new Date(2026, 5, 15);               // Monday 15 June 2026
  var KEY = "durham-hpc-days-2026-my-timetable";

  var $ = function (id) { return document.getElementById(id); };
  var cards = Array.prototype.slice.call(root.querySelectorAll(".session-card"));
  var rows = Array.prototype.slice.call(root.querySelectorAll(".week-grid .week-row:not(.week-header)"));
  var cols = Array.prototype.slice.call(root.querySelectorAll(".col"));
  var tabs = Array.prototype.slice.call(root.querySelectorAll(".day-tab"));
  var chips = Array.prototype.slice.call(root.querySelectorAll(".legend-item"));
  var search = $("programme-search"), filterText = $("filter-text"), clearFilters = $("clear-filters");
  var status = $("my-timetable-status");
  var btnMine = $("toggle-my-timetable"), btnIcs = $("export-my-timetable"), btnPrint = $("print-my-timetable"), btnClear = $("clear-my-timetable");
  var narrow = window.matchMedia("(max-width: 1000px)");

  var selected = new Set(), filters = new Set(), query = "", mineOnly = false, focus = "all";
  try { selected = new Set(JSON.parse(localStorage.getItem(KEY) || "[]")); } catch (e) {}

  function say(msg) { status.textContent = msg; }
  function id(c) { return c.dataset.sessionId; }
  function title(c) { return c.querySelector(".session-title").textContent.trim(); }
  function save() {
    try { localStorage.setItem(KEY, JSON.stringify(Array.from(selected))); }
    catch (e) { say("Your browser could not save your timetable. Check its storage settings."); }
  }

  /* Times come from the day and the HH:MM in start_time / end_time */
  function clock(text) { var m = /(\d{1,2}):(\d{2})/.exec(text || ""); return m ? [+m[1], +m[2]] : null; }
  cards.forEach(function (c) {
    var d = DAYS.indexOf(c.dataset.day), s = clock(c.dataset.start), e = clock(c.dataset.end);
    c._t = null;
    if (d < 0 || !s) return;
    var y = FIRST_DAY.getFullYear(), mo = FIRST_DAY.getMonth(), da = FIRST_DAY.getDate() + d;
    var start = new Date(y, mo, da, s[0], s[1]);
    var end = e ? new Date(y, mo, da, e[0], e[1]) : new Date(start.getTime() + 36e5);
    if (end <= start) end = new Date(start.getTime() + 36e5);
    c._t = { start: start, end: end };
  });

  function todayName() {
    var n = new Date(), d = Math.round((new Date(n.getFullYear(), n.getMonth(), n.getDate()) - FIRST_DAY) / 864e5);
    return d >= 0 && d < 5 ? DAYS[d] : null;
  }
  function fromHash() {
    var h = location.hash.slice(1).toLowerCase();
    return DAYS.filter(function (d) { return d.toLowerCase() === h; })[0] || null;
  }

  /* ---------- Render ---------- */
  function render() {
    var q = query.trim().toLowerCase(), matching = 0, now = new Date();

    root.dataset.focus = focus;
    root.style.setProperty("--cols", focus === "all" ? 5 : 1);
    tabs.forEach(function (t) { t.setAttribute("aria-pressed", String(t.dataset.day === focus)); });
    cols.forEach(function (el) { el.hidden = focus !== "all" && el.dataset.day !== focus; });

    cards.forEach(function (c) {
      var sel = selected.has(id(c));
      var match = (!filters.size || filters.has(c.dataset.sessionCategory)) && (!q || c.dataset.search.indexOf(q) > -1);
      if (match) matching++;

      c.hidden = mineOnly && !sel;
      c.classList.toggle("is-dim", !match);
      c.classList.toggle("is-selected", sel);
      c.classList.toggle("is-live", !!c._t && now >= c._t.start && now < c._t.end);

      var b = c.querySelector(".session-save");
      b.textContent = sel ? "\u2713" : "+";
      b.setAttribute("aria-pressed", String(sel));
      b.setAttribute("aria-label", (sel ? "Remove " : "Add ") + title(c) + (sel ? " from" : " to") + " your timetable");
    });

    rows.forEach(function (row) {
      if (row.classList.contains("is-fixed")) { row.hidden = false; return; }
      row.hidden = !Array.prototype.some.call(row.querySelectorAll(".session-card"), function (c) {
        return !c.hidden && (focus === "all" || c.dataset.day === focus);
      });
    });
    // Breaks with no sessions around them in the current view are just noise.
    rows.forEach(function (row, i) {
      if (!row.classList.contains("is-fixed")) return;
      var before = rows.slice(0, i).some(function (r) { return !r.classList.contains("is-fixed") && !r.hidden; });
      var after = rows.slice(i + 1).some(function (r) { return !r.classList.contains("is-fixed") && !r.hidden; });
      row.hidden = !(before && after);
    });

    chips.forEach(function (ch) {
      var n = cards.filter(function (c) { return c.dataset.sessionCategory === ch.dataset.category; }).length;
      ch.querySelector(".legend-count").textContent = n;
      ch.hidden = n === 0;
      ch.setAttribute("aria-pressed", String(filters.has(ch.dataset.category)));
    });

    var filtering = filters.size > 0 || q.length > 0;
    filterText.textContent = filtering ? matching + " of " + cards.length + " sessions match." : "Showing all sessions.";
    clearFilters.hidden = !filtering;

    var clashes = markClashes();
    var n = selected.size;
    $("my-timetable-count").textContent = n ? n + (n === 1 ? " session" : " sessions") + " in your timetable" : "Your timetable is empty";
    $("my-timetable-hint").textContent = n ? (clashes ? clashes + " with a time clash." : "No time clashes.") : "Select + on a session to add it.";
    btnMine.textContent = mineOnly ? "Show full programme" : "Show only my sessions";
    btnMine.setAttribute("aria-pressed", String(mineOnly));
    [btnMine, btnIcs, btnPrint, btnClear].forEach(function (b) { b.disabled = !n; });
  }

  function markClashes() {
    var picked = cards.filter(function (c) { return selected.has(id(c)) && c._t; }), total = 0;
    cards.forEach(function (c) {
      var note = c.querySelector(".session-clash");
      var others = selected.has(id(c)) && c._t ? picked.filter(function (o) {
        return o !== c && o._t.start < c._t.end && o._t.end > c._t.start;
      }) : [];
      c.classList.toggle("is-clash", others.length > 0);
      note.hidden = !others.length;
      note.textContent = others.length ? "Clashes with " + others.map(title).join(", ") : "";
      if (others.length) total++;
    });
    return total;
  }

  /* ---------- Day focus ---------- */
  function setFocus(day, replaceHash) {
    if (narrow.matches && day === "all") day = todayName() || "Monday";
    focus = day;
    if (replaceHash) history.replaceState(null, "", day === "all" ? location.pathname + location.search : "#" + day.toLowerCase());
    render();
  }
  tabs.forEach(function (t) { t.addEventListener("click", function () { setFocus(t.dataset.day, true); }); });
  window.addEventListener("hashchange", function () { var d = fromHash(); if (d) setFocus(d, false); });
  narrow.addEventListener("change", function () { setFocus(focus, false); });

  /* ---------- Filters and search ---------- */
  chips.forEach(function (ch) {
    ch.addEventListener("click", function () {
      var k = ch.dataset.category;
      if (filters.has(k)) filters["delete"](k); else filters.add(k);
      render();
    });
  });
  search.addEventListener("input", function () { query = search.value; render(); });
  clearFilters.addEventListener("click", function () { filters.clear(); query = ""; search.value = ""; render(); });
  root.addEventListener("keydown", function (e) {
    if (e.key === "Escape" && (filters.size || query)) { filters.clear(); query = ""; search.value = ""; render(); }
  });

  /* ---------- My timetable ---------- */
  root.addEventListener("click", function (e) {
    var b = e.target.closest(".session-save");
    if (!b) return;
    var c = b.closest(".session-card"), k = id(c);
    if (selected.has(k)) { selected["delete"](k); say("Removed from your timetable."); }
    else { selected.add(k); say("Added to your timetable."); }
    save(); render();
    var note = c.querySelector(".session-clash");
    if (selected.has(k) && !note.hidden) say(note.textContent + ".");
  });

  btnMine.addEventListener("click", function () {
    mineOnly = !mineOnly;
    say(mineOnly ? "Showing your sessions only." : "Showing the full programme.");
    render();
  });
  btnClear.addEventListener("click", function () {
    if (!selected.size || !confirm("Remove all " + selected.size + " sessions from your timetable?")) return;
    selected.clear(); mineOnly = false; save(); render(); say("Timetable cleared.");
  });

  /* Calendar export (.ics, floating local times) */
  function stamp(d) {
    var p = function (n) { return String(n).padStart(2, "0"); };
    return d.getFullYear() + p(d.getMonth() + 1) + p(d.getDate()) + "T" + p(d.getHours()) + p(d.getMinutes()) + "00";
  }
  function esc(s) { return String(s).replace(/[\\;,]/g, function (m) { return "\\" + m; }); }

  btnIcs.addEventListener("click", function () {
    var picked = cards.filter(function (c) { return selected.has(id(c)) && c._t; });
    if (!picked.length) { say("None of your sessions have a start time to export."); return; }
    var utc = new Date().toISOString().replace(/[-:]/g, "").replace(/\.\d+/, "");
    var lines = ["BEGIN:VCALENDAR", "VERSION:2.0", "PRODID:-//Durham HPC Days 2026//Programme//EN", "CALSCALE:GREGORIAN"];
    picked.forEach(function (c) {
      lines.push("BEGIN:VEVENT", "UID:" + id(c) + "@hpc-days-2026", "DTSTAMP:" + utc,
        "DTSTART:" + stamp(c._t.start), "DTEND:" + stamp(c._t.end),
        "SUMMARY:" + esc(title(c)), "LOCATION:" + esc(c.dataset.room || "Durham"),
        "URL:" + c.querySelector(".session-title a").href, "END:VEVENT");
    });
    lines.push("END:VCALENDAR");
    var a = document.createElement("a");
    a.href = URL.createObjectURL(new Blob([lines.join("\r\n")], { type: "text/calendar" }));
    a.download = "hpc-days-2026-my-timetable.ics";
    document.body.appendChild(a); a.click(); a.remove();
    say("Calendar file downloaded. Times are in Durham local time.");
  });

  /* Printing: your sessions if you have any, otherwise the whole week */
  var before = null;
  btnPrint.addEventListener("click", function () { window.print(); });
  window.addEventListener("beforeprint", function () {
    before = { mineOnly: mineOnly, focus: focus, filters: new Set(filters), query: query };
    if (selected.size) mineOnly = true;
    focus = "all"; filters.clear(); query = "";
    render();
  });
  window.addEventListener("afterprint", function () {
    if (!before) return;
    mineOnly = before.mineOnly; focus = before.focus; filters = before.filters; query = before.query; before = null;
    render();
  });

  /* ---------- Start ---------- */
  root.classList.add("is-ready");
  setFocus(fromHash() || (narrow.matches ? (todayName() || "Monday") : "all"), false);
});
</script>