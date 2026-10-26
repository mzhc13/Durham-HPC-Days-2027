---
layout: splash
title: "Sponsors"
permalink: /sponsors/
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

{% comment %} Settings {% endcomment %}
{% assign contact_name = "Alastair Basden" %}
{% assign contact_email = "a.g.basden@durham.ac.uk" %}

<div class="hpc" id="hpc">
  <div class="hpc-progress" aria-hidden="true"></div>

  <!-- ===== PAGE HEADER ===== -->
  <header class="hpc-pagehead" id="top">
    <div class="hpc-in">
      <nav class="hpc-crumbs" aria-label="Breadcrumb" data-reveal>
        <a href="{{ '/' | relative_url }}">Home</a><span aria-hidden="true">/</span><span aria-current="page">Sponsors</span>
      </nav>
      <p class="hpc-host" data-reveal style="--i:1">Call for sponsors</p>
      <h1 data-reveal style="--i:1">Sponsor Durham HPC Days 2027</h1>
      <p class="hpc-lede" data-reveal style="--i:2">Meet the researchers, developers, system administrators and vendors working with high-performance computing. Join us in Durham for a week of keynotes, talks, tutorials and workshops.</p>

      <p class="hpc-actions" data-reveal style="--i:4">
        <a class="hpc-btn hpc-btn-white" href="mailto:{{ contact_email }}?subject=Durham%20HPC%20Days%202027%20sponsorship">Express your interest</a>
        <a class="hpc-btn hpc-btn-ghost" href="#previous-sponsors">See our 2026 sponsors</a>
      </p>
    </div>
  </header>

  <!-- ===== WHY SPONSOR ===== -->
  <section class="hpc-section" id="why">
    <div class="hpc-in hpc-split">
      <div data-reveal>
        <h2>Why sponsor?</h2>
        <p>Durham HPC Days brings together the people who run and use research computing. Sponsoring puts you in the room with them: dedicated time on the programme, and a stand in the coffee and lunch room where attendees spend their breaks.</p>
        <p>We could not run the event without our sponsors and supporters, and we are keen to help you make the most of the week.</p>

      </div>
      <div data-reveal style="--i:1">
        <h2>At a glance</h2>
        <div class="sp-stats">
          <div class="sp-stat"><strong>230+</strong><span>attendees expected over the week</span></div>
          <div class="sp-stat"><strong>5 days</strong><span>12 to 16 July 2027</span></div>
          <div class="sp-stat"><strong>Table display</strong><span>Get your own table display to showcase your content</span></div>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== WHAT SPONSORS GET ===== -->
  <section class="hpc-section hpc-alt" id="benefits">
    <div class="hpc-in">
      <h2 data-reveal>What sponsors get</h2>
      <p class="hpc-sub" data-reveal style="--i:1">Four ways to meet the community during the week.</p>

      <div class="sp-cards" data-reveal style="--i:1">

        <article class="sp-card" style="--c: var(--s-keynote)">
          <p class="sp-label">Day to be confirmed</p>
          <h3>Sponsor session</h3>
          <ul class="sp-list">
            <li>A 2 to 3 minute slot to introduce yourself to the whole audience</li>
            <li>A 15 minute panel taking questions from the audience</li>


          </ul>
        </article>

        <article class="sp-card" style="--c: var(--s-tutorial)">
          <p class="sp-label">Throughout the event</p>
          <h3>Table-top display</h3>
          <ul class="sp-list">
            <li>A table of approximately 2 × 1 m, with two chairs</li>
            <li>Next to the coffee and lunch room</li>
            <li>Bring a banner and items for your table, including merchandise to give away</li>
          </ul>
        </article>

        <article class="sp-card" style="--c: var(--s-talk)">
          <p class="sp-label">Day to be confirmed</p>
          <h3>Treasure hunt</h3>
          <ul class="sp-list">
            <li>A treasure hunt for attendees, and for sponsors too if you wish</li>
            <li>Attendees ask you a question or get information from your stand or presentation to complete their answers</li>
            <li>A friendly way to start conversations</li>
          </ul>
        </article>

        <article class="sp-card" style="--c: var(--s-workshop)">
          <p class="sp-label">All week</p>
          <h3>Talks, tutorials and social</h3>
          <ul class="sp-list">
            <li>You are welcome to attend any of the talks or tutorials while you are here</li>
            <li>Stay for as much or as little of the week as you wish</li>
          </ul>
        </article>

      </div>
    </div>
  </section>

  <!-- ===== PLAN YOUR VISIT ===== -->
  <section class="hpc-section" id="visit">
    <div class="hpc-in hpc-split">
      <div data-reveal>
        <h2>Plan your visit</h2>
        <p>You are welcome to attend as much or as little of the event as you wish. The key sponsor day is <strong> yet to be confirmed</strong></p>
       
      </div>
      <div data-reveal style="--i:1">
        <h2>Provisional schedule</h2>
        <ol class="hpc-dates">
          <li><span>Yet to be confirmed</span>Call for sponsors closes</li>
          <li><span>Yet to be confirmed</span>Sponsor session and treasure hunt</li>
          <li class="hpc-final"><span>Yet to be confirmed</span>Stand moves if you are staying longer</li>
        </ol>
      </div>
    </div>
  </section>

  <!-- ===== CALL TO ACTION ===== -->
  <section class="hpc-band" id="contact">
    <div class="hpc-in hpc-split">
      <div data-reveal>
        <h2>Become a sponsor</h2>
        <p>Sponsorship details for 2027 are being finalised. Get in touch to express your interest, ask a question, or request more space or chairs for your stand.</p>
      </div>
      <div data-reveal style="--i:1">
        <h2>Contact</h2>
        <p>{{ contact_name }}<br><a href="mailto:{{ contact_email }}">{{ contact_email }}</a></p>
        <p class="hpc-actions">
          <a class="hpc-btn hpc-btn-white" href="mailto:{{ contact_email }}?subject=Durham%20HPC%20Days%202027%20sponsorship">Email us</a>
          <a class="hpc-btn hpc-btn-ghost" href="{{ '/' | relative_url }}">Back to Home</a>
        </p>
      </div>
    </div>
  </section>

  <!-- ===== 2026 SPONSORS ===== -->
  <section class="hpc-section hpc-alt" id="previous-sponsors">
    <div class="hpc-in">
      <h2 data-reveal>Our 2026 sponsors</h2>
      <p class="hpc-sub" data-reveal style="--i:1">Thank you to everyone who supported Durham HPC Days 2026.</p>

      <div class="sp-logos" data-reveal style="--i:1">
        <a class="sp-logo" href="https://www.ddn.com" target="_blank" rel="noopener noreferrer" aria-label="DDN"><img src="https://www.ddn.com/wp-content/uploads/2024/09/ddn-logo-dark-horizontal-rgb.jpg" alt="DDN" loading="lazy"></a>
        <a class="sp-logo" href="https://eu.fsastech.com/eu/" target="_blank" rel="noopener noreferrer" aria-label="Fsas Technologies"><img src="https://media.licdn.com/dms/image/v2/D4D0BAQFz2Hw6LVRJlg/company-logo_200_200/B4DZWPBwyvHYAI-/0/1741861359139?e=2147483647&v=beta&t=sLukj4LFeyoCCButXJ0ICGVDUN3dEz_FDbeicBq3pNM" alt="Fsas Technologies" loading="lazy"></a>
        <a class="sp-logo" href="https://www.novatech.co.uk/" target="_blank" rel="noopener noreferrer" aria-label="Novatech"><img src="https://media.licdn.com/dms/image/v2/D4E0BAQERb5GeBVwP7g/company-logo_200_200/company-logo_200_200/0/1688369383296/novatech_logo?e=2147483647&v=beta&t=DlfqUR3v9c8B9qftCRLVBJ4nlTTSYiolK0OFNqu5Fw8" alt="Novatech" loading="lazy"></a>
        <a class="sp-logo" href="https://ocf.co.uk/" target="_blank" rel="noopener noreferrer" aria-label="OCF"><img src="https://ocf.co.uk/images/logoblue.png" alt="OCF" loading="lazy"></a>
        <a class="sp-logo" href="https://vespertec.com/" target="_blank" rel="noopener noreferrer" aria-label="Vespertec"><img src="https://media.licdn.com/dms/image/v2/C4E0BAQEhA0V0YoOXGA/company-logo_200_200/company-logo_200_200/0/1676029024070/vesper_technologies_logo?e=2147483647&v=beta&t=TTfPTvl6bMW_7GtD21Z5wY8qMyoIW6nttrufzvEagKI" alt="Vespertec" loading="lazy"></a>
        <a class="sp-logo" href="https://www.dell.com/en-uk" target="_blank" rel="noopener noreferrer" aria-label="Dell Technologies"><img src="https://aeseurope.com/wp-content/uploads/2021/05/dell-technologies-vertical_logo.png" alt="Dell Technologies" loading="lazy"></a>
        <a class="sp-logo" href="https://www.stackhpc.com/" target="_blank" rel="noopener noreferrer" aria-label="StackHPC"><img src="https://avatars.githubusercontent.com/u/22750772?s=200&v=4" alt="StackHPC" loading="lazy"></a>
        <a class="sp-logo" href="https://spectralogic.com/" target="_blank" rel="noopener noreferrer" aria-label="Spectra Logic"><img src="https://spectralogic.com/wp-content/uploads/SpectraLogo-2023.webp" alt="Spectra Logic" loading="lazy"></a>
        <a class="sp-logo" href="https://www.peakaio.com/" target="_blank" rel="noopener noreferrer" aria-label="PEAK:AIO"><img src="https://www.peakaio.com/images/logos/peakaio-logo-org.png" alt="PEAK:AIO" loading="lazy"></a>
        <a class="sp-logo" href="https://www.amd.com/en.html" target="_blank" rel="noopener noreferrer" aria-label="AMD"><img src="https://media.licdn.com/dms/image/v2/D560BAQFCdxxVA_xhqQ/company-logo_200_200/B56ZnuIjafHUAM-/0/1760636844195/amd_logo?e=2147483647&v=beta&t=oM29UWcjmkCmT-aq0bZ_DEd-eqpPMQ-WR_FxQr-qHuM" alt="AMD" loading="lazy"></a>
        <a class="sp-logo" href="https://www.vastdata.com/" target="_blank" rel="noopener noreferrer" aria-label="VAST Data"><img src="https://media.datacenterdynamics.com/media/images/vast-stacked-logo-hex-blue.original.png" alt="VAST Data" loading="lazy"></a>
        <a class="sp-logo" href="https://www.cerio.ai/about/" target="_blank" rel="noopener noreferrer" aria-label="Cerio"><img src="https://media.licdn.com/dms/image/v2/D4E0BAQHXQBXfdTL5CQ/company-logo_200_200/company-logo_200_200/0/1696902111021/rockport_networks_inc__logo?e=2147483647&v=beta&t=FtlSAqR4iyzjknbR2_hDBhx7wRiP4_KOeXl6N2hMEeU" alt="Cerio" loading="lazy"></a>
        <a class="sp-logo" href="https://www.beegfs.io/c/" target="_blank" rel="noopener noreferrer" aria-label="BeeGFS"><img src="https://www.advancedclustering.com/wp-content/uploads/2022/04/BeeGFS_big.png" alt="BeeGFS" loading="lazy"></a>
        <a class="sp-logo" href="https://www.bios-it.co.uk/home.aspx" target="_blank" rel="noopener noreferrer" aria-label="BIOS-IT"><img src="{{ '/assets/images/biositlogo.png' | relative_url }}" alt="BIOS-IT" loading="lazy"></a>
        <a class="sp-logo" href="https://www.computacenter.com/en-gb" target="_blank" rel="noopener noreferrer" aria-label="Computacenter"><img src="{{ '/assets/images/computacenterlogo.png' | relative_url }}" alt="Computacenter" loading="lazy"></a>
        <a class="sp-logo" href="https://alces-flight.com/" target="_blank" rel="noopener noreferrer" aria-label="Alces Flight"><img src="https://alces-flight.com/wp-content/uploads/2023/11/Alces-Flight-KG-Logo.png" alt="Alces Flight" loading="lazy"></a>
        <a class="sp-logo" href="https://midasimmersion.com/" target="_blank" rel="noopener noreferrer" aria-label="Midas Immersion Cooling"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ600jBke7tEbherj_Qolde-FiHvrc6nuq-RA&s" alt="Midas Immersion Cooling" loading="lazy"></a>
        <a class="sp-logo" href="https://www.quantum.com" target="_blank" rel="noopener noreferrer" aria-label="Quantum"><img src="https://www.quantum.com/globalassets/redesign2021/quantum-logo-gradient.svg" alt="Quantum" loading="lazy"></a>
        <a class="sp-logo" href="https://www.cornelis.com" target="_blank" rel="noopener noreferrer" aria-label="Cornelis"><img src="{{ '/assets/images/cornelislogo.png' | relative_url }}" alt="Cornelis" loading="lazy"></a>
        <a class="sp-logo" href="https://www.durham.ac.uk/" target="_blank" rel="noopener noreferrer" aria-label="Durham University"><img src="https://durham.readthedocs.io/en/latest/_static/logo.png" alt="Durham University" loading="lazy"></a>
      </div>
    </div>
  </section>

  <button type="button" class="hpc-top" aria-label="Back to top">↑</button>
</div>

<style>
/* ==========================================================================
   PAGE-SPECIFIC STYLES (Sponsors)
   ========================================================================== */

/* Hide the theme's automatic page title (the hero already has an h1) */
#page-title, .page__title { display: none; }

/* ----- "At a glance" stats ----- */
.sp-stats { display: grid; grid-template-columns: repeat(3, minmax(0,1fr)); gap: 10px; }
.sp-stat { padding: 20px 18px; background: var(--card); border: 1px solid var(--line); border-top: 4px solid var(--purple-light); }
.sp-stat strong { display: block; color: var(--purple-light); font-size: clamp(28px, 3.4vw, 20px); font-weight: 800; letter-spacing: -.02em; line-height: 1.1; }
.sp-stat span { display: block; margin-top: 6px; color: var(--muted); font-size: 15px; line-height: 1.4; }

/* ----- Benefit cards: rectangles that grow slightly on hover (no colour change) ----- */
.sp-cards { display: grid; grid-template-columns: repeat(2, minmax(0,1fr)); gap: 18px; }
.sp-card {
  --c: var(--purple-light);
  position: relative; padding: 28px 28px 24px;
  background: var(--card);
  border: 1px solid var(--c) !important;
  border-radius: 0;
  transition: transform .25s ease, box-shadow .25s ease, border-color .25s ease;
}
.sp-card:hover { z-index: 2; transform: scale(1.02); border-color: var(--c); box-shadow: 0 14px 32px rgba(0,0,0,.45); }
.hpc .sp-card h3 { margin-bottom: 14px; color: var(--c); font-size: 26px; }
.hpc .sp-label { margin-bottom: 4px; color: var(--muted); font-size: 14px; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; }
.hpc .sp-list li { position: relative; margin-bottom: 8px; padding-left: 20px; color: var(--text); font-size: 16px; line-height: 1.55; }
.hpc .sp-list li:last-child { margin-bottom: 0; }
.hpc .sp-list li:before { content: ""; position: absolute; left: 0; top: .6em; width: 8px; height: 8px; background: var(--c); }

.hpc .sp-note { margin-top: 18px; color: var(--muted); font-size: 15px; }

/* ----- 2026 sponsor logo wall ----- */
.sp-logos { display: grid; grid-template-columns: repeat(auto-fill, minmax(190px, 1fr)); gap: 16px; border-radius: 10px; }
.hpc a.sp-logo {
  display: flex; align-items: center; justify-content: center;
  aspect-ratio: 3 / 2; padding: 16px;
  background: #fff; border: 1px solid #fff; border-radius: 0;
  transition: transform .25s ease, box-shadow .25s ease;
  border-radius: 10px;
}
.hpc a.sp-logo:hover,
.hpc a.sp-logo:focus-visible { transform: translateY(-4px); box-shadow: 0 12px 28px rgba(0,0,0,.45); }
.sp-logo img { display: block; max-width: 80%; max-height: 80%; object-fit: contain; }

@media (max-width: 900px) {
  .sp-cards { grid-template-columns: 1fr; }
}
@media (max-width: 680px) {
  .sp-stats { grid-template-columns: 1fr; }
  .sp-logos { grid-template-columns: repeat(2, minmax(0,1fr)); gap: 12px; }
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
})();
</script>