---
layout: splash
permalink: /
hidden: true
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Source+Sans+3:wght@400;600;700;800&display=swap" rel="stylesheet">

{% comment %}
  Settings. While the 2027 programme is being built, these point at the 2026 files.
  Switch programme_collection / programme_url to the 2027 versions when available.
  event_date: set to an ISO date/time (e.g. "2027-06-14T09:00:00") to switch on the countdown.
{% endcomment %}
{% assign programme_collection = "programme-days-2026" %}
{% assign programme_url = "/programme-week-2026/" %}
{% assign show_sessions = false %}
{% assign video_id = "" %}
{% assign contact_email = "" %}
{% assign event_date = "2027-07-12T09:00:00" %}
{% assign allowed = "workshop,talk,keynote,tutorial" | split: "," %}
{% assign sessions = "" | split: "," %}
{% if show_sessions and site[programme_collection] %}
  {% assign sessions = site[programme_collection] | sort: "start_time" | where_exp: "item", "allowed contains item.category" %}
{% endif %}

<div class="hpc" id="hpc" data-date="{{ event_date }}">
  <div class="hpc-progress" aria-hidden="true"></div>

  <header class="hpc-hero" id="top">
    <canvas class="hpc-net" aria-hidden="true"></canvas>
    <div class="hpc-in hpc-hero-in">
    <!--   <p class="hpc-host" data-reveal>Durham University </p> -->
     <h1 data-reveal style="--i:1">Durham HPC Days 2027</h1>
      <p class="hpc-date" data-reveal style="--i:1">
  <span class="hpc-date-days">12 to 16</span>
  <span class="hpc-date-month">July 2027</span>
  <span class="hpc-date-count" id="hpc-count"></span>
</p>
      <p class="hpc-lede" data-reveal style="--i:2">A week of keynotes, talks, tutorials and workshops on high-performance computing, data analysis and scientific software.</p>

      <dl class="hpc-facts" data-reveal style="--i:3">
        <div><dt>Dates</dt><dd>Monday 12 to Friday 16 July 2027</dd></div>
        <div><dt>Location</dt><dd>Durham, United Kingdom</dd></div>
        <div><dt>Registration</dt><dd>Opening soon</dd></div>
      </dl>

      <p class="hpc-actions" data-reveal style="--i:4">
        <a class="hpc-btn hpc-btn-white" href="{{ '/past/' | relative_url }}">View previous editions</a>
        <a class="hpc-btn hpc-btn-ghost" href="{{ '/sponsors/' | relative_url }}">Become a sponsor</a>
      </p>
    </div>
    <a class="hpc-scroll" href="#about" aria-label="Scroll to content"><span></span></a>
  </header>

  <section class="hpc-section" id="about">
    <div class="hpc-in hpc-split">
      <div data-reveal>
        <h2>About the event</h2>
        <p>Durham HPC Days brings together researchers, developers, system administrators and vendors to share what is working in high-performance computing, from applications and software to the systems that run them.</p>
        <p>Invited keynotes and contributed talks sit alongside hands-on tutorials and community workshops, with time for working meetings and informal conversation.</p>
        <ul class="hpc-chips" aria-label="Who attends">
          <li>Researchers</li><li>Developers</li><li>System administrators</li><li>Vendors</li>
        </ul>
      </div>
      <div data-reveal style="--i:1">
        <h2>Key dates</h2>
        <ol class="hpc-dates">
          <li><span>To be confirmed</span>Call for contributions opens</li>
          <li><span>To be confirmed</span>Submission deadline</li>
          <li><span>To be confirmed</span>Registration opens</li>
          <li><span>To be confirmed</span>Programme published</li>
          <li class="hpc-final"><span>12-16 July 2027</span>Durham HPC Days 2027</li>
        </ol>
      </div>
    </div>
  </section>



    <section class="hpc-band" id="contribute">
    <div class="hpc-in hpc-split">
      <div data-reveal>
        <h2>Call for submissions</h2>
        <p>Share your work with the HPC community in Durham, 12 to 16 July 2027. We invite proposals for workshops, talks, tutorials and meetings.</p>

       <p class="hpc-copyrow">
        <a class="hpc-btn hpc-btn-white" href="{{ '/call-for-submissions/' | relative_url }}">Call for submissions</a>
      </p>

      </div>
      
  <!--
  <div data-reveal style="--i:1">
    <h2>Join the conversation</h2>
    <p>Attendees talk through the CAKE Slack workspace. Join the workspace, then find the channel <strong>#hpc-days27</strong>.</p>
    <p class="hpc-copyrow">
      <a class="hpc-btn hpc-btn-white" href="https://join.slack.com/t/cake-dri/shared_invite/zt-3dvw46q4g-eode0z4zTvpzoBv~fsQv~w/">Join the CAKE Slack workspace</a>
      <button type="button" class="hpc-btn hpc-btn-ghost" data-copy="#hpc-days27">Copy channel name</button>
    </p>
  </div>
  -->

   </div>
  </section>


  <section class="hpc-section hpc-alt" id="programme">
    <div class="hpc-in">
      <h2 data-reveal>Explore the programme</h2>
      <p class="hpc-sub" data-reveal style="--i:1">Six ways to take part. Pick one to see what is planned.</p>
    </div>
    <div class="hpc-in hpc-tiles">
      <a class="hpc-tile t1" data-reveal style="--i:0" href="{{ '' | relative_url }}">
        <h3>Keynotes</h3>
        <p>Invited speakers on where HPC and research computing are heading.</p>
        <span class="hpc-go">Coming soon</span>
      </a>
      <a class="hpc-tile t2" data-reveal style="--i:1" href="{{ '' | relative_url }}">
        <h3>Tutorials</h3>
        <p>Hands-on sessions where you work through examples on real systems.</p>
        <span class="hpc-go">Coming soon</span>
      </a>
      <a class="hpc-tile t3" data-reveal style="--i:2" href="{{ '' | relative_url }}">
        <h3>Talks</h3>
        <p>Contributed presentations on applications, infrastructure and tools.</p>
        <span class="hpc-go">Coming soon</span>
      </a>
      <a class="hpc-tile t4" data-reveal style="--i:0" href="{{ '' | relative_url }}">
        <h3>Workshops</h3>
        <p>Longer, focused sessions on a single topic, led by the community.</p>
        <span class="hpc-go">Coming soon</span>
      </a>
      <a class="hpc-tile t5" data-reveal style="--i:1" href="{{ '' | relative_url }}">
        <h3>Meetings</h3>
        <p>Working meetings and user groups that run alongside the programme.</p>
        <span class="hpc-go">Coming soon</span>
      </a>
      <a class="hpc-tile t6" data-reveal style="--i:2" href="{{ '' | relative_url }}">
        <h3>Socials</h3>
        <p>Evening events and meals for meeting other attendees.</p>
        <span class="hpc-go">Coming soon</span>
      </a>
    </div>
  </section>

  <section class="hpc-section" id="watch">
    <div class="hpc-in hpc-split hpc-split-video">
      <div data-reveal>
        {% if video_id != "" %}
          <button class="hpc-video" type="button" data-id="{{ video_id }}" aria-label="Play video" style="background-image:url('https://img.youtube.com/vi/{{ video_id }}/hqdefault.jpg')"><span class="hpc-play"></span></button>
        {% else %}
          <div class="hpc-video hpc-video-empty" role="img" aria-label="Video placeholder"><span class="hpc-play"></span><span class="hpc-video-note">2026 recap video coming soon</span></div>
        {% endif %}
      </div>
      <div data-reveal style="--i:1">
        <h2>Watch</h2>
        <p>A short film from this year’s event will be added here. In the meantime, the recap from 2025 shows what a week at HPC Days looks like.</p>
        <p><a class="hpc-btn hpc-btn-purple" href="https://youtu.be/wPjtwACmaUg">Watch the 2025 recap</a></p>
      </div>
    </div>
  </section>

  {% if sessions.size > 0 %}
    <section class="hpc-section hpc-alt">
      <div class="hpc-in">
        <h2 data-reveal>Featured sessions</h2>
        <div class="hpc-filter" role="group" aria-label="Filter sessions">
          <button type="button" class="on" data-f="all">All</button>
          <button type="button" data-f="keynote">Keynotes</button>
          <button type="button" data-f="tutorial">Tutorials</button>
          <button type="button" data-f="talk">Talks</button>
          <button type="button" data-f="workshop">Workshops</button>
        </div>
        <ul class="hpc-cards">
          {% for s in sessions limit: 8 %}
            <li class="hpc-card hpc-{{ s.category | downcase }}" data-cat="{{ s.category | downcase }}">
              <a href="{{ s.url | relative_url }}">
                <span class="hpc-card-title">{{ s.title }}</span>
                <span class="hpc-card-meta">{{ s.day }}, {{ s.start_time }}–{{ s.end_time }}{% if s.room and s.room != "TBC" %}<br>{{ s.room }}{% endif %}</span>
              </a>
            </li>
          {% endfor %}
        </ul>
      </div>
    </section>
  {% endif %}



<!--
  <section class="hpc-section">
    <div class="hpc-in hpc-faq-wrap">
      <h2 data-reveal>Good to know</h2>
      <div class="hpc-faq" data-reveal style="--i:1">
        <details><summary>Who is it for?</summary><p>Researchers, developers, system administrators and vendors working with high-performance computing, data analysis and scientific software.</p></details>
        <details><summary>How do I stay up to date?</summary><p>Join the CAKE Slack workspace and find <strong>#hpc-days27</strong>. Dates and registration details will also be published on this page.</p></details>
        <details><summary>Can I contribute a session?</summary><p>Yes. We will invite talks, tutorials and workshops from the community. Submission details will appear under “Call for contributions”.</p></details>
        <details><summary>Can my organisation sponsor the event?</summary><p>Yes. Visit the <a href="{{ '/sponsors/' | relative_url }}">sponsors page</a> to find out how.</p></details>
      </div>
    </div>
  </section>
-->
<section class="hpc-section hpc-alt" id="previous">
  <div class="hpc-in hpc-split hpc-split-video">
    <div class="hpc-photo" data-reveal>
      <img src="{{ '/assets/images/eva-blue-banner.png' | relative_url }}" alt="Attendees in a session at a previous Durham HPC Days" loading="lazy">
    </div>
    <div data-reveal style="--i:1">
      <h2>Previous Durham HPC Days editions</h2>
      <p>Explore previous editions of Durham HPC Days, including highlights, photos, and links to full programmes and documentation.</p>
      <p class="hpc-copyrow">
        <a class="hpc-btn hpc-btn-white" href="{{ '/past-hpc-days/' | relative_url }}">Browse Previous Editions</a>
      </p>
    </div>
  </div>
</section>

  <dialog class="hpc-lightbox" aria-label="Photo viewer">
    <button type="button" class="hpc-close" aria-label="Close">×</button>
    <img alt="">
  </dialog>
  <button type="button" class="hpc-top" aria-label="Back to top">↑</button>
  <div class="hpc-toast" role="status" aria-live="polite"></div>
</div>

<style>
/* ==========================================================================
   1. GLOBAL / PAGE RESET
   Base fonts and overrides of the Jekyll theme wrappers (full-width layout)
   ========================================================================== */
html { scroll-behavior: smooth; background: #07121A; }
body, h1, h2, h3, h4 { font-family: "Source Sans 3", system-ui, -apple-system, "Segoe UI", sans-serif; }

.page__content, .page__inner-wrap, .wrapper, .initial-content {
  max-width: 100% !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
  margin-top: 0 !important;
}


/* ==========================================================================
   2. DESIGN TOKENS
   ========================================================================== */

/* Session-type colours (reuse these in the programme timetable) */
:root {
  --s-keynote:  #D79BDD;
  --s-tutorial: #5BB4E5;
  --s-talk:     #4FC3B0;
  --s-workshop: #F0B35E;
  --s-meeting:  #B5D96B;
  --s-social:   #E88FB4;
}

/* Brand palette (purple-led, tinted darks) + root container */
.hpc {
  --purple: #68246D;
  --purple-light: #C98ACF;
  --purple-soft: #EBD6EE;
  --bg: #0E0812;
  --alt: #160D1B;
  --card: #20132A;
  --line: #3E2A4B;
  --text: #F6F1F8;
  --muted: #B8A8C2;
  --ink: #1D0B20;           /* dark text used on coloured backgrounds */

  position: relative;
  width: 100vw;
  margin-left: calc(50% - 50vw);
  overflow-x: clip;
  background: var(--bg);
  color: var(--text);
  font: 400 16px/1.6 "Source Sans 3", system-ui, sans-serif;
}
.hpc *, .hpc *:before, .hpc *:after { box-sizing: border-box; }


/* ==========================================================================
   3. TYPOGRAPHY, LINKS AND LAYOUT HELPERS
   ========================================================================== */
.hpc h1, .hpc h2, .hpc h3 { font-family: inherit; font-weight: 800; line-height: 1.12; margin: 0 0 14px; color: var(--text); }
.hpc h2 { font-size: clamp(26px, 3.2vw, 34px); letter-spacing: -.01em;  border-bottom-color: #f4e8f8 !important; }
.hpc p  { margin: 0 0 14px; font-size: 17px; line-height: 1.65; color: var(--text); }
.hpc ul, .hpc ol { list-style: none; margin: 0; padding: 0; }

.hpc a { color: var(--purple-light); text-underline-offset: 4px; }
.hpc a:hover { color: var(--purple-soft); }
.hpc a:focus-visible,
.hpc button:focus-visible,
.hpc summary:focus-visible { outline: 3px solid var(--purple-soft); outline-offset: 3px; }

.hpc-in  { max-width: 1100px; margin: auto; padding: 0 28px; }   /* centred content wrapper */
.hpc-sub { color: var(--muted) !important; margin-bottom: 28px !important; }


/* ==========================================================================
   4. SCROLL PROGRESS BAR (top of the page)
   ========================================================================== */
.hpc-progress {
  position: fixed; top: 0; left: 0; z-index: 100;
  width: 100%; height: 3px;
  background: linear-gradient(90deg, var(--purple), var(--purple-light), var(--purple-soft));
  transform: scaleX(0); transform-origin: left;
}


/* ==========================================================================
   5. BUTTONS
   ========================================================================== */
.hpc .hpc-btn {
  display: inline-block; padding: 11px 22px;
  border: 2px solid var(--purple); border-radius: 6px;
  font: 700 16px/1.3 inherit; text-decoration: none; cursor: pointer;
  transition: background .2s, color .2s, border-color .2s, transform .2s;
}
.hpc .hpc-btn:hover { transform: translateY(-1px); }

/* Small purple button */
.hpc .hpc-btn-sm { padding: 7px 15px; font-size: 14px; background: var(--purple); color: #fff !important; }
.hpc .hpc-btn-sm:hover { background: var(--purple-light); border-color: var(--purple-light); color: var(--ink) !important; }

/* White button */
.hpc .hpc-btn-white { background: #F3F0F6; color: var(--ink) !important; border-color: #F3F0F6; }
.hpc .hpc-btn-white:hover { background: var(--purple-soft); border-color: var(--purple-soft); }

/* Purple button */
.hpc .hpc-btn-purple { background: var(--purple); color: #fff !important; }
.hpc .hpc-btn-purple:hover { background: var(--purple-light); border-color: var(--purple-light); color: var(--ink) !important; }

/* Ghost (outline) button */
.hpc .hpc-btn-ghost { background: transparent; color: #fff !important; border-color: rgba(255,255,255,.7); }
.hpc .hpc-btn-ghost:hover { background: rgba(255,255,255,.12); border-color: #fff; }


/* ==========================================================================
   6. HERO (banner, network canvas, title, key facts)
   ========================================================================== */
.hpc-hero {
  position: relative; display: flex; align-items: flex-end;
  min-height: 78vh; padding: 90px 0 70px; overflow: hidden;
  background: url("https://github.com/mzhc13/Durham-HPC-Days-2027/blob/main/assets/images/2027.jpeg?raw=true") center 40% / cover no-repeat;
}
/* Purple gradient overlay on top of the banner image */
.hpc-hero:before {
  content: ""; position: absolute; inset: 0; z-index: 0;
  background:
    linear-gradient(160deg, rgba(16,4,20,.97) 0%, rgba(40,13,46,.95) 55%, rgba(43, 15, 47, 0.92) 100%),
    linear-gradient(to top, var(--bg), transparent 30%);
}
/* Animated compute-cluster canvas */
.hpc-net { position: absolute; inset: 0; z-index: 1; width: 100%; height: 100%; }

.hpc-hero-in { position: relative; z-index: 2; width: 100%; pointer-events: none; }
.hpc-hero-in a, .hpc-hero-in button { pointer-events: auto; }

.hpc-host  { margin-bottom: 10px !important; color: var(--purple-soft) !important; font-size: 15px !important; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; }
.hpc-hero h1 { max-width: 1200px; margin-bottom: 18px; color: #fff; font-size: clamp(40px, 6vw, 90px); letter-spacing: -.025em; }
.hpc-lede  { max-width: 620px; margin: 0 0 28px !important; color: #EAF1F6 !important; font-size: 20px !important; }

/* Dates / Location / Registration */
.hpc-facts { display: flex; flex-wrap: wrap; gap: 16px 44px; max-width: 700px; margin: 0 0 28px; padding-top: 18px; border-top: 1px solid rgba(255,255,255,.3); }
.hpc-facts dt { color: var(--purple-soft); font-size: 14px; }
.hpc-facts dd { margin: 0; font-size: 17px; font-weight: 700; color: #fff; }

.hpc-actions { display: flex; flex-wrap: wrap; gap: 12px; margin: 0 !important; }

/* Animated "scroll down" indicator */
.hpc-scroll { position: absolute; bottom: 20px; left: 50%; z-index: 2; width: 26px; height: 42px; margin-left: -13px; border: 2px solid rgba(255,255,255,.55); border-radius: 14px; }
.hpc-scroll span { position: absolute; left: 50%; top: 8px; width: 4px; height: 8px; margin-left: -2px; background: #fff; border-radius: 2px; animation: hpc-dot 1.8s ease-in-out infinite; }
@keyframes hpc-dot {
  0%   { opacity: 0; transform: translateY(0); }
  40%  { opacity: 1; }
  100% { opacity: 0; transform: translateY(14px); }
}

/* Big date block (hero) */
.hpc-date { display: flex; flex-wrap: wrap; align-items: baseline; gap: 4px 14px; margin: 0 0 20px !important; padding-left: 16px; border-left: 4px solid var(--purple-light); }
.hpc .hpc-date-days  { color: #fff; font-size: clamp(36px, 5vw, 56px); font-weight: 800; letter-spacing: -.02em; line-height: 1; }
.hpc .hpc-date-month { color: var(--purple-soft); font-size: clamp(20px, 2.6vw, 28px); font-weight: 700; letter-spacing: .04em; text-transform: uppercase; }
.hpc .hpc-date-count { flex-basis: 100%; color: var(--muted); font-size: 15px; font-weight: 600; }
.hpc .hpc-date-count:empty { display: none; }

/* ==========================================================================
   7. SECTIONS (generic blocks, two-column split, chips)
   ========================================================================== */
.hpc-section { padding: 72px 0; background: var(--bg); }
.hpc-alt     { background: var(--alt); }

.hpc-split       { display: grid; grid-template-columns: 1.2fr 1fr;  gap: 32px 64px; align-items: start; }
.hpc-split-video { grid-template-columns: 1.25fr 1fr; align-items: center; }

/* "Who attends" pills */
.hpc-chips { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 18px !important; }
.hpc-chips li { padding: 5px 14px; border: 1px solid var(--line); border-radius: 999px; background: var(--card); color: var(--muted); font-size: 14px; font-weight: 600; }


/* ==========================================================================
   8. KEY DATES TIMELINE
   ========================================================================== */
.hpc-dates { margin-left: 6px !important; border-left: 2px solid var(--line) !important; }
.hpc-dates li { position: relative; padding: 0 0 20px 26px; font-weight: 600; line-height: 1.4; }
.hpc-dates li:last-child { padding-bottom: 0; }
.hpc-dates li:before {
  content: ""; position: absolute; left: -8px; top: 4px;
  width: 14px; height: 14px; border-radius: 50%;
  background: var(--bg); border: 2px solid var(--purple-light);
  transition: background .3s, box-shadow .3s;
}
.hpc-dates li:hover:before,
.hpc-final:before { background: var(--purple-light); box-shadow: 0 0 0 5px rgba(201,138,207,.22); }
.hpc-dates span { display: block; margin-bottom: 2px; color: var(--muted); font-size: 14px; font-weight: 400; }


/* ==========================================================================
   9. PROGRAMME TILES (Keynotes, Tutorials, Talks, Workshops, Meetings, Socials)
   The fill colour on hover comes from the per-tile --c variable.
   ========================================================================== */


.hpc-tiles {display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 18px;}
/* Base tile */
.hpc a.hpc-tile {  --c: var(--purple-light); position: relative; display: flex; flex-direction: column; justify-content: flex-end;

  min-height: 220px;
  padding: 26px 26px 24px;
  overflow: hidden;

  background: var(--card);
  border: 1px solid var(--line);
  color: var(--text);
  text-decoration: none;

  /* Animate movement, shadow, background and border */
  transition:
    box-shadow 0.3s ease,
    background-color 0.4s ease,
    border-color 0.3s ease;
}

/* Tile text */
.hpc .hpc-tile h3 {
  font-size: 26px;
  color: #fff;
  transition: color 0.3s ease;
}

.hpc .hpc-tile p {
  margin-bottom: 16px;
  color: #D7E2EA;
  font-size: 16px;
  transition: color 0.3s ease;
}

.hpc .hpc-go {
  color: #fff;
  font-weight: 700;
  font-size: 15px;
  transition: color 0.3s ease;
}

.hpc .hpc-go::after {
  content: "→";
  display: inline-block;
  margin-left: 8px;
  transition: transform 0.3s ease;
}

.hpc .hpc-tile:hover .hpc-go::after {
  transform: translateX(6px);
}

/* Lift and colour the tile on hover or keyboard focus */
.hpc a.hpc-tile:hover,
.hpc a.hpc-tile:focus-visible {
  transform: translateY(-5px);
  background-color: var(--c);
  border-color: var(--c);
  box-shadow: 0 14px 32px rgba(0, 0, 0, 0.4);
}

/* Dark text on the coloured background */
.hpc a.hpc-tile:hover h3,
.hpc a.hpc-tile:hover p,
.hpc a.hpc-tile:hover .hpc-go,
.hpc a.hpc-tile:focus-visible h3,
.hpc a.hpc-tile:focus-visible p,
.hpc a.hpc-tile:focus-visible .hpc-go {
  color: var(--ink);
}

/* Colour assigned to each tile */
.hpc a.hpc-tile.t1 { --c: var(--s-keynote); }
.hpc a.hpc-tile.t2 { --c: var(--s-tutorial); }
.hpc a.hpc-tile.t3 { --c: var(--s-talk); }
.hpc a.hpc-tile.t4 { --c: var(--s-workshop); }
.hpc a.hpc-tile.t5 { --c: var(--s-meeting); }
.hpc a.hpc-tile.t6 { --c: var(--s-social); }

.js .hpc a.hpc-tile.in:hover,
.js .hpc a.hpc-tile.in:focus-visible {
  transform: translateY(-5px);
}

/* ==========================================================================
   10. VIDEO (thumbnail button, iframe, empty placeholder)
   ========================================================================== */
.hpc-video {
  position: relative; display: block; width: 100%; aspect-ratio: 16/9; padding: 0;
  border: 1px solid var(--line); border-radius: 10px; overflow: hidden;
  background: var(--card) center/cover no-repeat; cursor: pointer;
}
.hpc-video iframe { position: absolute; inset: 0; width: 100%; height: 100%; border: 0; }

/* Placeholder shown when no video_id is set */
.hpc-video-empty { display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 14px; cursor: default; background: linear-gradient(135deg, #2A0E2E, #4A1C52); }
.hpc-video-note  { color: #F0DFF2; font-size: 15px; font-weight: 600; }

/* Play button */
.hpc-play { position: relative; display: block; width: 62px; height: 62px; border: 2px solid #fff; border-radius: 50%; background: var(--purple); transition: transform .2s, background .2s; }
.hpc-play:after { content: ""; position: absolute; top: 17px; left: 24px; border: 12px solid transparent; border-right: 0; border-left: 18px solid #fff; }
.hpc-video:not(.hpc-video-empty) .hpc-play { position: absolute; top: 50%; left: 50%; margin: -31px 0 0 -31px; }
.hpc-video:not(.hpc-video-empty):hover .hpc-play { transform: scale(1.1); background: var(--purple-light); }


/* ==========================================================================
   11. FEATURED SESSION CARDS + CATEGORY FILTER
   Only rendered when show_sessions is true in the page settings.
   ========================================================================== */
.hpc-cards { display: grid; grid-template-columns: repeat(auto-fill, minmax(230px, 1fr)); gap: 16px; }

.hpc-card {
  background: var(--card);
  border: 1px solid var(--line);
  border-top: 4px solid var(--session-colour, var(--purple-light));
  border-radius: 8px; overflow: hidden;
  transition: background .25s ease, transform .2s, box-shadow .2s;
}
.hpc-card[hidden] { display: none; }   /* used by the filter buttons */

/* HOVER: fill the card with its category colour */
.hpc-card:hover {
  background: var(--session-colour, var(--purple-light));
  transform: translateY(-3px);
  box-shadow: 0 10px 22px rgba(0,0,0,.35);
}

.hpc .hpc-card a { display: flex; flex-direction: column; height: 100%; padding: 16px; color: var(--text); text-decoration: none; }
.hpc .hpc-card a:hover { background: transparent; color: var(--text); }

.hpc-card-title { margin-bottom: 10px; font-size: 17px; font-weight: 700; line-height: 1.4; transition: color .25s; }
.hpc-card-meta  { margin-top: auto; color: var(--muted); font-size: 14px; transition: color .25s; }

/* Dark text on the coloured background when hovering */
.hpc-card:hover .hpc-card-title,
.hpc-card:hover .hpc-card-meta { color: var(--ink); }

/* Automatic colour per session category */
.hpc-keynote  { --session-colour: var(--s-keynote); }
.hpc-tutorial { --session-colour: var(--s-tutorial); }
.hpc-talk     { --session-colour: var(--s-talk); }
.hpc-workshop { --session-colour: var(--s-workshop); }
.hpc-meeting,
.hpc-meetings { --session-colour: var(--s-meeting); }
.hpc-social,
.hpc-socials  { --session-colour: var(--s-social); }


/* ==========================================================================
   12. CALL-TO-ACTION BAND (Call for contributions / Slack)
   ========================================================================== */
/*.hpc-band { padding: 64px 0; background: linear-gradient(135deg, #2A0E2E, #45184B 55%, var(--purple)); border-block: 1px solid rgba(255,255,255,.12); }*/
.hpc-band { padding: 64px 0; background: var(--purple); border-block: 1px solid rgba(255,255,255,.12); }
.hpc-band a:not(.hpc-btn) { color: var(--purple-soft); }
.hpc-copyrow { display: flex; flex-wrap: wrap; gap: 10px; }
.hpc-band h2 { width: 1200px;}


/* ==========================================================================
   13. FAQ ACCORDION ("Good to know")
   ========================================================================== */
.hpc-faq-wrap { max-width: 820px; }
.hpc-faq details { border-bottom: 1px solid var(--line); }
.hpc-faq summary { position: relative; padding: 18px 40px 18px 0; font-size: 18px; font-weight: 700; cursor: pointer; list-style: none; }
.hpc-faq summary::-webkit-details-marker { display: none; }
/* "+" icon that rotates into an "x" when open */
.hpc-faq summary:after { content: "+"; position: absolute; right: 6px; top: 50%; transform: translateY(-50%); color: var(--purple-light); font-size: 26px; font-weight: 400; transition: transform .25s; }
.hpc-faq details[open] summary:after { transform: translateY(-50%) rotate(45deg); }
.hpc-faq details p { margin: 0 0 18px; color: var(--muted); animation: hpc-open .3s ease; }
@keyframes hpc-open {
  from { opacity: 0; transform: translateY(-6px); }
  to   { opacity: 1; transform: none; }
}


/* ==========================================================================
   14. PREVIOUS EVENTS (photo gallery + lightbox)
   ========================================================================== */
.hpc-gallery { display: grid; grid-template-columns: repeat(3, minmax(0,1fr)); gap: 14px; margin-top: 18px; }
.hpc-gallery button { padding: 0; border: 1px solid var(--line); border-radius: 10px; overflow: hidden; background: none; cursor: zoom-in; }
.hpc-gallery img { display: block; width: 100%; height: 220px; object-fit: cover; transition: transform .5s; }
.hpc-gallery button:hover img { transform: scale(1.06); }

/* Links to previous editions */
.hpc-prev { display: flex; flex-wrap: wrap; gap: 8px 28px; margin: 22px 0 0 !important; }
.hpc-prev a { font-weight: 600; }

/* Fullscreen photo viewer */
.hpc-lightbox { max-width: 92vw; max-height: 90vh; padding: 0; border: 0; border-radius: 10px; background: transparent; }
.hpc-lightbox::backdrop { background: rgba(0,10,18,.88); }
.hpc-lightbox img { display: block; max-width: 92vw; max-height: 88vh; border-radius: 10px; }
.hpc-close { position: absolute; top: 8px; right: 8px; width: 38px; height: 38px; border: 0; border-radius: 50%; background: var(--purple); color: #fff; font-size: 24px; line-height: 1; cursor: pointer; }

/* Photo in the "Previous editions" block */
.hpc-photo img { display: block; width: 100%; height: 340px; object-fit: cover; border: 1px solid #fff; }

@media (max-width: 680px) {
  .hpc-photo img { height: 210px; }
}

/* ==========================================================================
   15. FLOATING HELPERS (back-to-top button, toast message)
   ========================================================================== */
.hpc-top {
  position: fixed; right: 22px; bottom: 22px; z-index: 70;
  width: 46px; height: 46px; border: 1px solid rgba(255,255,255,.25); border-radius: 50%;
  background: var(--purple); color: #fff; font-size: 20px; cursor: pointer;
  opacity: 0; transform: translateY(12px); pointer-events: none;
  transition: opacity .25s, transform .25s, background .2s;
}
.hpc-top.show  { opacity: 1; transform: none; pointer-events: auto; }
.hpc-top:hover { background: var(--purple-light); color: var(--ink); }

.hpc-toast {
  position: fixed; left: 50%; bottom: 28px; z-index: 80;
  padding: 10px 20px; border-radius: 8px; background: #fff; color: var(--ink); font-weight: 700;
  opacity: 0; transform: translate(-50%, 14px); pointer-events: none;
  transition: opacity .25s, transform .25s;
}
.hpc-toast.show { opacity: 1; transform: translate(-50%, 0); }


/* ==========================================================================
   16. REVEAL-ON-SCROLL ANIMATION
   Elements with data-reveal fade in; --i staggers the delay.
   ========================================================================== */
.js .hpc [data-reveal] { opacity: 0; transform: translateY(16px); transition: opacity .55s ease, transform .55s ease; transition-delay: calc(var(--i,0) * 70ms); }
.js .hpc [data-reveal].in { opacity: 1; transform: none; }


/* ==========================================================================
   17. ACCESSIBILITY: REDUCED MOTION
   ========================================================================== */
@media (prefers-reduced-motion: reduce) {
  html { scroll-behavior: auto; }
  .js .hpc [data-reveal] { opacity: 1; transform: none; transition: none; }
  .hpc-progress, .hpc-scroll span { display: none; }
  .hpc *, .hpc *:before, .hpc *:after { transition: none !important; animation: none !important; }
}


/* ==========================================================================
   18. RESPONSIVE
   ========================================================================== */

/* Tablet: 2 tile columns */
@media (max-width: 900px) {
  .hpc-tiles { grid-template-columns: repeat(2, minmax(0,1fr)); }
}

/* Mobile: single column layout */
@media (max-width: 680px) {
  .hpc-in { padding: 0 20px; }
  .hpc-hero { min-height: 0; padding: 70px 0; }
  .hpc-section { padding: 48px 0; }
  .hpc-split, .hpc-split-video, .hpc-gallery, .hpc-tiles { grid-template-columns: 1fr; }
  .hpc a.hpc-tile { min-height: 170px; }
  .hpc-gallery img { height: 190px; }
  .hpc-scroll { display: none; }
}
</style>

<script>
(function () {
  var root = document.getElementById('hpc');
  if (!root) return;
  document.documentElement.classList.add('js');
  var reduce = window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  var $ = function (s, c) { return (c || root).querySelector(s); };
  var $$ = function (s, c) { return Array.prototype.slice.call((c || root).querySelectorAll(s)); };

  /* Reveal on scroll */
  var items = $$('[data-reveal]');
  if ('IntersectionObserver' in window && !reduce) {
    var io = new IntersectionObserver(function (es) {
      es.forEach(function (e) { if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target); } });
    }, { threshold: .12, rootMargin: '0px 0px -40px 0px' });
    items.forEach(function (el) { io.observe(el); });
  } else { items.forEach(function (el) { el.classList.add('in'); }); }

  /* Progress bar + back to top */
  var bar = $('.hpc-progress'), topBtn = $('.hpc-top'), ticking = false;
  function update() {
    var max = document.documentElement.scrollHeight - window.innerHeight;
    if (bar && max > 0) bar.style.transform = 'scaleX(' + Math.min(1, window.scrollY / max) + ')';
    topBtn.classList.toggle('show', window.scrollY > 700);
    ticking = false;
  }
  window.addEventListener('scroll', function () { if (!ticking) { ticking = true; requestAnimationFrame(update); } }, { passive: true });
  update();
  topBtn.addEventListener('click', function () { window.scrollTo({ top: 0, behavior: reduce ? 'auto' : 'smooth' }); });

/* Countdown (only if event_date is set) */
var cd = $('#hpc-count'), iso = root.getAttribute('data-date');
if (cd && iso) {
  var target = new Date(iso).getTime();
  if (!isNaN(target)) {
    var tick = function () {
      var d = target - Date.now();
      if (d <= 0) { cd.textContent = 'Happening now'; return; }
      var days = Math.floor(d / 864e5), h = Math.floor(d % 864e5 / 36e5);
      cd.textContent = days + ' days ' + h + ' h to go';
    };
    tick(); setInterval(tick, 60000);
  }
}

  /* Session filter */
  var fbtns = $$('.hpc-filter button');
  fbtns.forEach(function (b) {
    b.addEventListener('click', function () {
      var f = b.getAttribute('data-f');
      fbtns.forEach(function (x) { x.classList.toggle('on', x === b); });
      $$('.hpc-card').forEach(function (c) { c.hidden = f !== 'all' && c.getAttribute('data-cat') !== f; });
    });
  });

  /* FAQ: one open at a time */
  var dets = $$('.hpc-faq details');
  dets.forEach(function (d) {
    d.addEventListener('toggle', function () { if (d.open) dets.forEach(function (o) { if (o !== d) o.open = false; }); });
  });

  /* Copy to clipboard + toast */
  var toast = $('.hpc-toast'), tt;
  function say(msg) { toast.textContent = msg; toast.classList.add('show'); clearTimeout(tt); tt = setTimeout(function () { toast.classList.remove('show'); }, 2200); }
  $$('[data-copy]').forEach(function (b) {
    b.addEventListener('click', function () {
      var txt = b.getAttribute('data-copy');
      if (navigator.clipboard) navigator.clipboard.writeText(txt).then(function () { say('Copied ' + txt); }, function () { say('Copy failed. Channel: ' + txt); });
      else say('Channel: ' + txt);
    });
  });

  /* Lightbox */
  var lb = $('.hpc-lightbox'), lbImg = $('img', lb);
  $$('.hpc-gallery button').forEach(function (b) {
    b.addEventListener('click', function () {
      lbImg.src = b.getAttribute('data-full'); lbImg.alt = $('img', b).alt;
      if (lb.showModal) lb.showModal(); else lb.setAttribute('open', '');
    });
  });
  $('.hpc-close', lb).addEventListener('click', function () { lb.close(); });
  lb.addEventListener('click', function (e) { if (e.target === lb) lb.close(); });

  /* Video */
  var v = $('button.hpc-video');
  if (v) v.addEventListener('click', function () {
    var f = document.createElement('iframe');
    f.src = 'https://www.youtube-nocookie.com/embed/' + v.getAttribute('data-id') + '?autoplay=1&rel=0';
    f.allow = 'autoplay; encrypted-media; picture-in-picture; fullscreen';
    f.allowFullscreen = true; f.title = 'Event video';
    v.innerHTML = ''; v.style.backgroundImage = 'none'; v.appendChild(f);
  });

  
  var cv = $('.hpc-net'), hero = $('.hpc-hero');
  if (cv && cv.getContext) {
    var ctx = cv.getContext('2d'), W, H, cell, cols, rows, act, tint, ok, jobs = [];
    var mouse = { x: -999, y: -999 }, running = true, frame = 0;
    // 
    var pal = ['215,155,221', '91,180,229', '79,195,176', '240,179,94', '181,217,107', '232,143,180'];

    function size() {
      var r = hero.getBoundingClientRect(), dpr = Math.min(window.devicePixelRatio || 1, 2);
      W = r.width; H = r.height;
      cv.width = W * dpr; cv.height = H * dpr; ctx.setTransform(dpr, 0, 0, dpr, 0, 0);
      cell = W < 680 ? 22 : 30;
      cols = Math.ceil(W / cell); rows = Math.ceil(H / cell);
      act = new Float32Array(cols * rows);
      tint = new Uint8Array(cols * rows);
      ok = new Uint8Array(cols * rows);
      jobs = [];

      // 
      var topLimit = H * (W < 680 ? .14 : .12);
      var side = Math.max(0, (W - 1100) / 2);
      for (var y = 0; y < rows; y++) for (var x = 0; x < cols; x++) {
        var inTop = (y + 1) * cell <= topLimit;
        var inSide = (x + 1) * cell <= side || x * cell >= W - side;
        ok[y * cols + x] = (inTop || inSide) ? 1 : 0;
      }
      if (reduce) { for (var k = 0; k < 14; k++) spawn(true); draw(); }
    }

    function fits(x, y, w, h) {
      for (var j = 0; j < w * h; j++) if (!ok[(y + Math.floor(j / w)) * cols + x + j % w]) return false;
      return true;
    }

    // 
    function spawn(still) {
      for (var t = 0; t < 12; t++) {
        var w = 2 + Math.floor(Math.random() * 4), h = 1 + Math.floor(Math.random() * 3);
        if (cols <= w || rows <= h) return;
        var x = Math.floor(Math.random() * (cols - w)), y = Math.floor(Math.random() * (rows - h));
        if (!fits(x, y, w, h)) continue;
        var life = 260 + Math.random() * 320;
        jobs.push({ x: x, y: y, w: w, h: h, c: Math.floor(Math.random() * pal.length), age: still ? life / 2 : 0, life: life });
        return;
      }
    }

    function draw() {
      ctx.clearRect(0, 0, W, H);
      var i, j, idx;

      // 
      for (i = jobs.length - 1; i >= 0; i--) {
        var jb = jobs[i];
        if (!reduce) jb.age++;
        if (jb.age >= jb.life) { jobs.splice(i, 1); continue; }
        var env = Math.min(1, jb.age / 20) * Math.min(1, (jb.life - jb.age) / 50);
        for (j = 0; j < jb.w * jb.h; j++) {
          var cx = jb.x + j % jb.w, cy = jb.y + Math.floor(j / jb.w);
          idx = cy * cols + cx;
          var v = (.5 + .4 * ((cx * 7 + cy * 13) % 5) / 4) * env;
          if (v > act[idx]) { act[idx] = v; tint[idx] = jb.c; }
        }
      }

      // 
      if (mouse.x > 0 && !reduce) {
        var R = 110, c0 = Math.max(0, Math.floor((mouse.x - R) / cell)), c1 = Math.min(cols - 1, Math.floor((mouse.x + R) / cell));
        var r0 = Math.max(0, Math.floor((mouse.y - R) / cell)), r1 = Math.min(rows - 1, Math.floor((mouse.y + R) / cell));
        for (var ry = r0; ry <= r1; ry++) for (var cx2 = c0; cx2 <= c1; cx2++) {
          idx = ry * cols + cx2;
          var d = Math.hypot((cx2 + .5) * cell - mouse.x, (ry + .5) * cell - mouse.y);
          //
          var k = ok[idx] ? .6 : .3;
          if (d < R) { var hv = k * (1 - d / R); if (hv > act[idx]) { act[idx] = hv; tint[idx] = 0; } }
        }
      }

      //
      var s = cell - 5;
      for (var y = 0; y < rows; y++) for (var x = 0; x < cols; x++) {
        idx = y * cols + x;
        ctx.fillStyle = 'rgba(255,255,255,.05)';
        ctx.fillRect(x * cell + 2.5, y * cell + 2.5, s, s);
        if (act[idx] > .02) {
          ctx.fillStyle = 'rgba(' + pal[tint[idx]] + ',' + (act[idx] * .7) + ')';
          ctx.fillRect(x * cell + 2.5, y * cell + 2.5, s, s);
          if (!reduce) act[idx] *= .965;
        }
      }
    }

    function loop() {
      if (!running) return;
      frame++;
      if (frame % 30 === 0 && jobs.length < 12) spawn();
      draw();
      requestAnimationFrame(loop);
    }

    hero.addEventListener('mousemove', function (e) { var r = hero.getBoundingClientRect(); mouse.x = e.clientX - r.left; mouse.y = e.clientY - r.top; });
    hero.addEventListener('mouseleave', function () { mouse.x = mouse.y = -999; });
    window.addEventListener('resize', size);
    size();
    if (!reduce) {
      if ('IntersectionObserver' in window) {
        new IntersectionObserver(function (es) {
          var vis = es[0].isIntersecting;
          if (vis && !running) { running = true; loop(); } else if (!vis) running = false;
        }).observe(hero);
      }
      loop();
    }
  }




})();
</script>
