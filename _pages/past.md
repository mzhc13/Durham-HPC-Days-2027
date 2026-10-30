---
layout: splash
title: "Past HPC Days"
permalink: /past/
hidden: true
---

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Source+Sans+3:wght@400;600;700;800&display=swap" rel="stylesheet">

{% comment %}
  Shared styles: save the CSS file as /assets/css/hpc-days.css (same one used by the home page).
  Page-specific styles (editions list) are in the <style> block at the bottom of this file.
{% endcomment %}
<link rel="stylesheet" href="{{ '/assets/css/hpc-days.css' | relative_url }}">

<div class="hpc" id="hpc">
  <div class="hpc-progress" aria-hidden="true"></div>

  <!-- ===== HERO ===== -->


  <header class="hpc-pagehead" id="top">
  <div class="hpc-in">
    <nav class="hpc-crumbs" aria-label="Breadcrumb" data-reveal>
      <a href="{{ '/' | relative_url }}">Home</a><span aria-hidden="true">/</span><span aria-current="page">Past Durham HPC Days</span>
    </nav>
    <p class="hpc-host" data-reveal style="--i:1">PREVIOUS EDITIONS</p>
    <h1 data-reveal style="--i:1">Past Durham HPC Days</h1>
    <p class="hpc-lede" data-reveal style="--i:2">Explore previous editions of Durham HPC Days, including highlights, photos, and links to full programmes and documentation.</p>

    <p class="hpc-actions" data-reveal style="--i:4">
      <a class="hpc-btn hpc-btn-white" href="#editions">Browse the editions</a>
      <a class="hpc-btn hpc-btn-ghost" href="{{ '/' | relative_url }}">Back to Home</a>
    </p>
  </div>
</header>

  <!-- ===== EDITIONS ===== -->
  <section class="hpc-section" id="editions">
    <div class="hpc-in">
      <h2 data-reveal>Previous editions</h2>
      <p class="hpc-sub" data-reveal style="--i:1">Each edition has its own website with the full programme.</p>

      <div class="hpc-editions">

  <article class="hpc-edition e0" data-reveal style="--i:0">
    <div class="hpc-ed-year" aria-hidden="true">2026</div>
    <div class="hpc-ed-body">
    <h3>Durham HPC Days 2026</h3>
     <!--<p class="hpc-ed-label">Full programme</p>-->  
    <p>The 2026 edition was our biggest yet, bringing together more than 230 attendees across a full week of keynotes, tutorials, workshops and contributed talks. Most sessions were recorded and are available to watch on the event website.</p>
    <a class="hpc-btn hpc-btn-purple" href="https://hpc-days.github.io/Durham-HPC-Days-2026/">Visit the 2026 website →</a>
  </div>
</article>

  <article class="hpc-edition e1" data-reveal style="--i:0">
    <div class="hpc-ed-year" aria-hidden="true">2025</div>
    <div class="hpc-ed-body">
      <h3>Durham HPC Days 2025</h3>
    <!--<p class="hpc-ed-label">Full programme</p>-->  
      <p>The 2025 edition focused on advanced GPU programming, large-scale parallel optimisation, hands-on profiling, and modern HPC workflows. Researchers, RSEs, and developers from multiple scientific fields participated in sessions, tutorials, and collaborative discussions.</p>
      <a class="hpc-btn hpc-btn-purple" href="https://durham.readthedocs.io/en/latest/hpcdays2025/index.html">Visit the 2025 website →</a>
    </div>
  </article>

  <article class="hpc-edition e2" data-reveal style="--i:1">
    <div class="hpc-ed-year" aria-hidden="true">2024</div>
    <div class="hpc-ed-body">
      <h3>Durham HPC Days 2024</h3>
      <!--<p class="hpc-ed-label">Full programme</p>-->  
      <p>The 2024 event focused on the evolving demands faced by compute centres and research computing groups. Core topics included:</p>
      <a class="hpc-btn hpc-btn-purple" href="https://scicomp.webspace.durham.ac.uk/events/code_performance_series/durham-hpc-days-2024/">Visit the 2024 website →</a>
    </div>
  </article>

  <article class="hpc-edition e3" data-reveal style="--i:2">
    <div class="hpc-ed-year" aria-hidden="true">2023</div>
    <div class="hpc-ed-body">
      <h3>Durham HPC Days 2023</h3>
       <!--<p class="hpc-ed-label">Full programme</p>-->  
      <p>The 2023 event focused on exploring the community’s transition from homogeneous to increasingly heterogeneous supercomputing architectures, focusing on how to adapt algorithms, workflows and quantities of interest to new hardware; the role of performance portability; lessons learned from prototype and experimental systems within ExCALIBUR and the integration of core computer science and applied mathematics with domain sciences.</p>
      <a class="hpc-btn hpc-btn-purple" href="https://tobiasweinzierl.webspace.durham.ac.uk/research/workshops/durham-hpc-days-spring-2023/">Visit the 2023 website →</a>
    </div>
  </article>

</div>
</div>
  </section>

  <!-- ===== PHOTO HIGHLIGHTS ===== -->
  <section class="hpc-section hpc-alt" id="photos">
    <div class="hpc-in">
      <h2 data-reveal>Photo highlights</h2>
      <div class="hpc-gallery">
        <button type="button" data-reveal style="--i:0" data-full="{{ '/assets/images/Sessions.jpg' | relative_url }}" aria-label="Enlarge photo: attendees in a session"><img src="{{ '/assets/images/Sessions.jpg' | relative_url }}" alt="Attendees in a session" loading="lazy"></button>
        <button type="button" data-reveal style="--i:1" data-full="{{ '/assets/images/food-truck.jpg' | relative_url }}" aria-label="Enlarge photo: food truck during a break"><img src="{{ '/assets/images/food-truck.jpg' | relative_url }}" alt="Food truck during a break" loading="lazy"></button>
        <button type="button" data-reveal style="--i:2" data-full="{{ '/assets/images/social.png' | relative_url }}" aria-label="Enlarge photo: attendees at the social event"><img src="{{ '/assets/images/social.png' | relative_url }}" alt="Attendees at the social event" loading="lazy"></button>
      </div>
    </div>
  </section>

  <!-- ===== LOOKING FORWARD ===== -->
  <section class="hpc-band" id="forward">
    <div class="hpc-in hpc-split">
      <div data-reveal>
        <h2>📈 Looking Forward</h2>
        <p>Durham HPC Days continues to grow each year, expanding into new areas such as sustainable HPC, AI-accelerated workflows, and advanced research software engineering.</p>
      </div>
      <div data-reveal style="--i:1">
        <p class="hpc-actions">
          <a class="hpc-btn hpc-btn-white" href="{{ '/' | relative_url }}">Back to Home</a>
          <a class="hpc-btn hpc-btn-ghost" href="{{ '/sponsors/' | relative_url }}">Become a sponsor</a>
        </p>
      </div>
    </div>
  </section>

  <dialog class="hpc-lightbox" aria-label="Photo viewer">
    <button type="button" class="hpc-close" aria-label="Close">×</button>
    <img alt="">
  </dialog>
  <button type="button" class="hpc-top" aria-label="Back to top">↑</button>
</div>

<style>
/* ==========================================================================
   PAGE-SPECIFIC STYLES (Past HPC Days)
   ========================================================================== */

/* Hide the theme's automatic page title (the hero already has an h1) */
#page-title, .page__title { display: none; }

/* Shorter hero for secondary pages */
.hpc-hero.hpc-hero-sm { min-height: 46vh; padding: 80px 0 56px; }

/* ----- Editions list ----- */
.hpc-editions { display: grid; gap: 18px; }

/* Base card: square rectangle with a coloured accent strip on the left */
.hpc-edition {
  --c: var(--purple-light);
  display: grid; grid-template-columns: 190px 1fr; gap: 12px 34px; align-items: center;
  padding: 32px 34px;
  background: var(--card);
  border: 1px solid var(--line);
  /*border-left: 6px solid var(--c);*/
  border-radius: 0;
  transition: transform .25s ease, box-shadow .25s ease, border-color .25s ease;
}

.hpc-edition.e0 { --c: var(--s-social); }
.hpc-edition.e1 { --c: var(--s-tutorial); }
.hpc-edition.e2 { --c: var(--s-talk); }
.hpc-edition.e3 { --c: var(--s-workshop); }

/* Card content */
.hpc-ed-year { color: var(--c); font-size: clamp(48px, 6vw, 72px); font-weight: 800; letter-spacing: -.03em; line-height: 1; border-right: 0.5px solid var(--line); align-self: stretch; display: flex; align-items: center; }

.hpc .hpc-edition h3 { margin-bottom: 4px; font-size: 26px; }
.hpc .hpc-ed-label { margin-bottom: 12px; color: var(--muted); font-size: 14px; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; }
.hpc .hpc-edition .hpc-chips { margin: 0 0 18px !important; }

/* HOVER / KEYBOARD FOCUS: card grows slightly (no colour change) */
.hpc .hpc-edition:hover,
.hpc .hpc-edition:focus-within {
  position: relative; z-index: 2;
  transform: scale(1.02);
  border-color: var(--c);
  box-shadow: 0 14px 32px rgba(0,0,0,.45);
}
/* ...and its button highlights */
.hpc .hpc-edition:hover .hpc-btn,
.hpc .hpc-edition:focus-within .hpc-btn {
  background: var(--purple-light);
  border-color: var(--purple-light);
  color: var(--ink) !important;
}

/* Reveal-on-scroll override: the generic [data-reveal].in rule resets transform and
   adds a stagger delay, which would block the hover scale. This keeps the fade-in
   but lets hover work instantly once the card is visible. */
.js .hpc .hpc-edition[data-reveal].in {
  transition: opacity .55s ease calc(var(--i, 0) * 70ms), transform .25s ease, box-shadow .25s ease, border-color .25s ease;
}
.js .hpc .hpc-edition[data-reveal].in:hover,
.js .hpc .hpc-edition[data-reveal].in:focus-within { transform: scale(1.02); }

@media (max-width: 680px) {
  .hpc-edition { grid-template-columns: 1fr; padding: 24px 22px; }
  .hpc-ed-year { font-size: 52px; }
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
})();
</script>