---
layout: splash
title: "Call for submissions"
permalink: /call-for-submissions/
hidden: true
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Source+Sans+3:wght@400;600;700;800&display=swap" rel="stylesheet">

{% comment %}
  Shared styles: /assets/css/hpc-days.css (same file as the other pages).
  Page-specific styles are in the <style> block at the bottom of this file.
{% endcomment %}
<link rel="stylesheet" href="{{ '/assets/css/hpc-days.css' | relative_url }}">

{% comment %}
  Settings.
  submit_url: if you have a submission form (Google Form, EasyChair, etc.), put its URL here
              and every "Submit" button will point to it. If left empty, the buttons open an
              email to contact_email with the proposal type already in the subject.
  Deadlines are in the cards below (data-deadline attributes and visible dates).
{% endcomment %}
{% assign submit_url = "" %}
{% assign contact_email = "" %}

{% capture mail_workshop %}mailto:{{ contact_email }}?subject=Durham%20HPC%20Days%202027%3A%20Workshop%20proposal{% endcapture %}
{% capture mail_talk %}mailto:{{ contact_email }}?subject=Durham%20HPC%20Days%202027%3A%20Talk%20proposal{% endcapture %}
{% capture mail_tutorial %}mailto:{{ contact_email }}?subject=Durham%20HPC%20Days%202027%3A%20Tutorial%20proposal{% endcapture %}
{% capture mail_meeting %}mailto:{{ contact_email }}?subject=Durham%20HPC%20Days%202027%3A%20Meeting%20proposal{% endcapture %}
{% assign href_workshop = submit_url | default: mail_workshop %}
{% assign href_talk = submit_url | default: mail_talk %}
{% assign href_tutorial = submit_url | default: mail_tutorial %}
{% assign href_meeting = submit_url | default: mail_meeting %}

<div class="hpc" id="hpc">
  <div class="hpc-progress" aria-hidden="true"></div>

  <!-- ===== PAGE HEADER ===== -->
  <header class="hpc-pagehead" id="top">
    <div class="hpc-in">
      <nav class="hpc-crumbs" aria-label="Breadcrumb" data-reveal>
  <a href="{{ '/' | relative_url }}">Home</a>
  <span aria-hidden="true">/</span>
  <span aria-current="page">Call for submissions</span>
</nav>
      <p class="hpc-host" data-reveal style="--i:1">Durham HPC Days 2027</p>
      <h1 data-reveal style="--i:1">Call for submissions</h1>
      <p class="hpc-lede" data-reveal style="--i:2">Share your work with the HPC community in Durham, 12 to 16 July 2027. We invite proposals for workshops, talks, tutorials and meetings.</p>

    </div>
  </header>

  <!-- ===== HOW IT WORKS + DEADLINES ===== -->
  <section class="hpc-section" id="how">
    <div class="hpc-in hpc-split">
      <div data-reveal>
        <h2>Contribute to the programme</h2>
        <p>Durham HPC Days brings together researchers, developers, system administrators and vendors. The programme is built from contributions by the community, and we welcome proposals from all of these groups.</p>
        <p>Below you will find a call for each type of session, with a description and what we need from you. Please read the requirements for the format you are interested in, then use its button to send us your proposal.</p>
        <p>Not sure which format fits your idea? Get in touch and we will be happy to help.</p>
      </div>
      <div data-reveal style="--i:1">
        <h2>Deadlines</h2>
        <ol class="hpc-dates">
          <li><span>Friday 6 November 2027</span>Calls open</li>
          <li><span>Friday 15 January 2027</span>Calls for Workshops, talks and tutorials close</li>
          <li><span>Friday 19 March 2027</span>Call for Meetings closes</li>
          <li class="hpc-final"><span>12 to 16 July 2027</span>Durham HPC Days 2027</li>
        </ol>
      </div>
    </div>
  </section>

  <!-- ===== THE FOUR CALLS ===== -->
  <section class="hpc-section hpc-alt" id="calls">
    <div class="hpc-in">
      <h2 data-reveal>Open calls</h2>
      <p class="hpc-sub" data-reveal style="--i:1">Four ways to take part. Each has its own description, requirements and deadline.</p>

<div class="cs-calls">

  <!-- WORKSHOPS -->
  <article class="cs-card" id="workshops" style="--c: var(--s-workshop)" data-reveal>
    <div class="cs-main">
      <p class="cs-label">Call for workshops</p>
      <h3>Workshops</h3>
      <p class="cs-deadline"><span class="cs-deadline-label">Deadline</span><strong>Friday 15 January 2027</strong><span class="cs-status" data-deadline="2027-01-15T23:59:00"></span></p>
      <p>Workshops are longer, focused sessions on a single topic, organised and led by the community. They are a space for in-depth discussion, sharing experience and working together on a shared problem in high-performance computing, data analysis or scientific software.</p>
    </div>
    <div class="cs-req">
      <h4>Requirements</h4>
      <ul class="cs-list">
        <li>A title and a short description of the topic and the goals of the workshop</li>
        <li>The name, affiliation and contact details of the organiser or organisers</li>
        <li>The intended audience and expected level of experience</li>
        <li>A proposed outline of the programme, including any planned speakers or activities</li>
        <li>Any equipment or computing needs</li>
      </ul>
      <p class="cs-action"><a class="hpc-btn hpc-btn-purple" href="{{ href_workshop }}">Submit a workshop proposal</a></p>
    </div>
  </article>

  <!-- TALKS -->
  <article class="cs-card" id="talks" style="--c: var(--s-talk)" data-reveal>
    <div class="cs-main">
      <p class="cs-label">Call for talks</p>
      <h3>Talks</h3>
      <p class="cs-deadline"><span class="cs-deadline-label">Deadline</span><strong>Friday 15 January 2027</strong><span class="cs-status" data-deadline="2027-01-15T23:59:00"></span></p>
      <p>Talks are contributed presentations on applications, infrastructure and tools. We are looking for speakers who can share what is working in high-performance computing, from the software and applications researchers run to the systems that support them.</p>
    </div>
    <div class="cs-req">
      <h4>Requirements</h4>
      <ul class="cs-list">
        <li>A title and a short abstract</li>
        <li>The name, affiliation and contact email of the speaker</li>
        <li>The topic area</li>
      </ul>
      <p class="cs-action"><a class="hpc-btn hpc-btn-purple" href="{{ href_talk }}">Submit a talk proposal</a></p>
    </div>
  </article>

  <!-- TUTORIALS -->
  <article class="cs-card" id="tutorials" style="--c: var(--s-tutorial)" data-reveal>
    <div class="cs-main">
      <p class="cs-label">Call for tutorials</p>
      <h3>Tutorials</h3>
      <p class="cs-deadline"><span class="cs-deadline-label">Deadline</span><strong>Friday 15 January 2027</strong><span class="cs-status" data-deadline="2027-01-15T23:59:00"></span></p>
      <p>Tutorials are hands-on sessions where participants work through examples on real systems. They suit topics that people learn best by doing, such as a tool, a programming approach or a workflow that attendees can take back to their own work.</p>
    </div>
    <div class="cs-req">
      <h4>Requirements</h4>
      <ul class="cs-list">
        <li>A title, a short abstract and the learning outcomes</li>
        <li>The name, affiliation and contact details of the instructor or instructors</li>
        <li>The target audience and any prerequisites, such as skills or software</li>
        <li>Hands-on material that participants can work through, such as exercises or examples</li>
        <li>The expected duration and the maximum number of participants</li>
        <li>Technical requirements, such as access to systems, accounts or software to install</li>
      </ul>
      <p class="cs-action"><a class="hpc-btn hpc-btn-purple" href="{{ href_tutorial }}">Submit a tutorial proposal</a></p>
    </div>
  </article>

  <!-- MEETINGS -->
  <article class="cs-card" id="meetings" style="--c: var(--s-meeting)" data-reveal>
    <div class="cs-main">
      <p class="cs-label">Call for meetings</p>
      <h3>Meetings</h3>
      <p class="cs-deadline"><span class="cs-deadline-label">Deadline</span><strong>Friday 19 March 2027</strong><span class="cs-status" data-deadline="2027-03-19T23:59:00"></span></p>
      <p>Meetings are working meetings and user groups that run alongside the main programme. If your group, project or community would benefit from meeting in person while many of its members are in Durham, this is the place to ask for a slot.</p>
    </div>
    <div class="cs-req">
      <h4>Requirements</h4>
      <ul class="cs-list">
        <li>The name of the group or meeting, and a short description of its purpose</li>
        <li>The name and contact details of the organiser</li>
        <li>Whether the meeting is open to all attendees or by invitation</li>
        <li>The expected number of participants</li>
        <li>Preferred length and timing</li>
      </ul>
      <p class="cs-action"><a class="hpc-btn hpc-btn-purple" href="{{ href_meeting }}">Submit a meeting proposal</a></p>
    </div>
  </article>

</div>
</div>
  </section>

  <!-- ===== QUESTIONS ===== -->
  <section class="hpc-band" id="questions">
    <div class="hpc-in hpc-split">
      <div data-reveal>
        <h2>Questions?</h2>
        <p>If you are unsure which format suits your idea, or you have a question about a requirement, get in touch before the deadline.</p>
      </div>
      <div data-reveal style="--i:1">
        <p><a href="mailto:{{ contact_email }}">{{ contact_email }}</a></p>
        <p class="hpc-actions">
          <a class="hpc-btn hpc-btn-white" href="mailto:{{ contact_email }}?subject=Durham%20HPC%20Days%202027%3A%20Question%20about%20submissions">Email us</a>
          <a class="hpc-btn hpc-btn-ghost" href="{{ '/' | relative_url }}">Back to Home</a>
        </p>
      </div>
    </div>
  </section>

  <button type="button" class="hpc-top" aria-label="Back to top">↑</button>
</div>

<style>
/* ==========================================================================
   PAGE-SPECIFIC STYLES (Call for submissions)
   ========================================================================== */

/* Jump links in the header */
.cs-jump { display: flex; flex-wrap: wrap; gap: 10px; margin: 0 !important; }
.hpc .cs-jump a {
  display: inline-block; padding: 7px 18px;
  border: 1px solid rgba(255,255,255,.5); border-radius: 999px;
  color: #fff; font-size: 15px; font-weight: 700; text-decoration: none;
  transition: background .2s, border-color .2s, color .2s;
}
.hpc .cs-jump a:hover { background: #fff; border-color: #fff; color: var(--ink); }

/* Stack of calls */
.cs-calls { display: grid; gap: 22px; }

/* Call card: rectangle, two columns (description | requirements) */
.cs-card {
  --c: var(--purple-light);
  display: grid; grid-template-columns: 1fr 1.1fr; gap: 20px 44px;
  padding: 32px 34px; scroll-margin-top: 24px;
  background: var(--card);
  border: 2px solid var(--c);
  border-radius: 0;
}
.js .hpc .cs-card[data-reveal].in {
  transition: opacity .55s ease calc(var(--i, 0) * 70ms), box-shadow .25s ease;
}
.cs-card:hover {  z-index: 2; transform: scale(1.02); border-color: var(--c); box-shadow: 0 14px 32px rgba(0,0,0,.45);  }

.hpc .cs-label { margin-bottom: 4px; color: var(--muted); font-size: 14px; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; }
.hpc .cs-card h3 { margin-bottom: 16px; color: var(--c); font-size: clamp(28px, 3.4vw, 36px); }
.hpc .cs-card h4 { margin: 0 0 12px; color: #fff; font-size: 18px; font-weight: 800; }

/* Deadline box */
.hpc .cs-deadline {
  display: flex; flex-wrap: wrap; align-items: baseline; gap: 4px 12px;
  margin: 0 0 18px; padding: 12px 16px;
  background: rgba(255,255,255,.04); border-left: 4px solid var(--c);
  font-size: 16px;
}
.cs-deadline-label { color: var(--muted); font-size: 13px; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; }
.cs-deadline strong { color: #fff; font-size: 18px; }
.cs-status { color: var(--c); font-size: 14px; font-weight: 700; }
.cs-status:empty { display: none; }
.cs-status.closed { color: #F4A3A3; }

/* Requirements list (square bullets in the card colour) */
.hpc .cs-list li { position: relative; margin-bottom: 9px; padding-left: 20px; color: var(--text); font-size: 16px; line-height: 1.55; }
.hpc .cs-list li:before { content: ""; position: absolute; left: 0; top: .6em; width: 8px; height: 8px; background: var(--c); }
.hpc .cs-action { margin: 22px 0 0; }

@media (max-width: 900px) {
  .cs-card { grid-template-columns: 1fr; padding: 26px 22px; }
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
    }, { threshold: .08, rootMargin: '0px 0px -40px 0px' });
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

  /* Deadline status: "N days left" / "Last day" / "Closed" */
  $$('[data-deadline]').forEach(function (el) {
    var t = new Date(el.getAttribute('data-deadline')).getTime();
    if (isNaN(t)) return;
    function refresh() {
      var d = t - Date.now();
      if (d <= 0) { el.textContent = 'Closed'; el.classList.add('closed'); return; }
      var days = Math.ceil(d / 864e5);
      el.textContent = days <= 1 ? 'Last day' : days + ' days left';
    }
    refresh(); setInterval(refresh, 3600000);
  });
})();
</script>