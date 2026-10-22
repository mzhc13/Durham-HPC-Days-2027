---
layout: splash
title: "Catch Up on HPC Days"
permalink: /recordings/
classes: wide
---

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
  overflow: hidden;
}


.ws-hero__overlay {
  position:absolute;
  inset:0;
  background:
    linear-gradient(rgba(0,0,0,0.35),rgba(0,0,0,0.35)),
    linear-gradient(
      135deg,
      rgba(46,15,58,0.95),
      rgba(109,44,122,0.75)
    );
}


.ws-hero__grid {
  position:absolute;
  inset:0;
  background-image:
    linear-gradient(rgba(255,255,255,0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.05) 1px, transparent 1px);
  background-size:48px 48px;
}


.ws-hero__content {
  position:relative;
  z-index:2;
  padding:0 3rem 3rem;
}


.ws-hero h1 {
  font-size:clamp(2.4rem,5vw,4rem);
  font-weight:400;
  color:white;
  margin:0;
}


.ws-hero__sub {
  color:rgba(255,255,255,0.75);
  font-size:1.1rem;
  max-width:650px;
}


.recordings-disclaimer{
  max-width:1200px;
  margin:1rem auto 1rem;
  padding:1rem 1rem;
  background:#f5f7fa;
  border-left:6px solid #68246D;
  border-radius:12px;
  color:#444;
  line-height:1.7;
  font-size:1rem;
  box-shadow:0 4px 12px rgba(0,0,0,0.05);
}

.recordings-disclaimer h3{
  margin:0 0 .75rem;
  color:#002A41;
  font-size:0.9rem;
}

.recordings-disclaimer p{
  margin:0;
  font-size:0.7rem;
}

.description {
  max-width:1200px;
  text-align:center;
  font-size:1.1rem;
  line-height:1.7;
  color:#555;
}


.recordings-grid {

  display:grid;
  grid-template-columns:
    repeat(auto-fit,minmax(300px,1fr));

  gap:2rem;

  max-width:1200px;
  margin:2rem auto 5rem;
  padding:0 1rem;

}

.recording-card {
  background:white;
  border-radius:18px;
  overflow:hidden;

  box-shadow:
    0 10px 25px rgba(0,0,0,0.08);

  transition:
    transform .25s ease,
    box-shadow .25s ease;

  border-top:6px solid #68246D;

  display:flex;
  flex-direction:column;
}



.recording-card:hover {

  transform:translateY(-6px);

  box-shadow:
    0 18px 35px rgba(0,0,0,0.15);

}


.video-container {

  aspect-ratio:16/9;
  background:#000;

}


.video-container iframe {

  width:100%;
  height:100%;
  border:0;

}


.recording-content {
  padding:1.5rem;

  display:flex;
  flex-direction:column;
  flex-grow:1;
}


.recording-title {

  font-size:1.15rem;
  font-weight:700;
  color:#002A41;
  line-height:1.4;
  margin-bottom:1rem;

}


.meta {

  font-size:.85rem;
  color:#555;
  margin-bottom:1rem;
  line-height:1.5;

}


.badge {

 display:inline-block;
 padding:.35rem .8rem;
 border-radius:999px;

 background:#002A41;
 color:white;

 font-size:.75rem;
 font-weight:600;

 margin-bottom:1rem;

}


.recording-buttons {
  display:flex;
  gap:.2rem;
  flex-wrap:wrap;

  margin-top:auto;
}

.recording-buttons a {

 padding:.45rem 1rem;
 border-radius:999px;

 background:#002A41;
 color:white!important;

 font-size:.8rem;
 font-weight:600;

}


.recording-buttons a:hover {


 background:rgb(67, 115, 137);

}


@media(max-width:768px){

.ws-hero{
height:35vh;
min-height:200px;
background-attachment:scroll;
}

.ws-hero__content{
padding:0 1.5rem 2rem;
}

.recordings-grid{
padding:0 1rem;
}

}


</style>


<section class="ws-hero">

<div class="ws-hero__overlay"></div>
<div class="ws-hero__grid"></div>

<div class="ws-hero__content">

<p style="color:white;opacity:.7;">
Durham HPC Days 2026
</p>

<h1>Session Recordings</h1>

<p class="ws-hero__sub">
Missed a session? Catch up with recordings and download presentation slides from Durham HPC Days 2026.
</p>

</div>

</section>


<div class="recordings-disclaimer">

<h3>Recording and Privacy Notice</h3>

<p>
Please note that only recordings for which we received permission from the presenters have been published. Some sessions include only the talks of speakers who consented to having their presentations shared, and therefore may not represent the complete session.
</p>

<p>
To respect the privacy of participants, discussion periods, audience questions, and other interactive sections may have been edited or removed. We thank all speakers and attendees for helping us make these resources available.
</p>

</div>




<h2 style="text-align:center; margin-top:3rem;">
  Session recordings
</h2>

<section class="recordings-grid">

{% for session in site.programme-days-2026 %}
  {% if session.recording %}

<div class="recording-card">

<div class="video-container">
<iframe
src="{{ session.recording }}"
title="{{ session.title }}"
allowfullscreen>
</iframe>
</div>

<div class="recording-content">

<div class="badge">
{{ session.category | capitalize }}
</div>

<div class="recording-title">
{{ session.title }}
</div>

<div class="meta">
{% if session.speaker %}
<strong>Speakers:</strong><br>
{{ session.speaker }}
{% endif %}
</div>


<div class="meta">
{% if session.lead %}
<strong>Lead:</strong><br>
{{ session.lead }}
{% endif %}
</div>

<div class="recording-buttons">

<a href="{{ session.youtube_url }}" 
   target="_blank" 
   rel="noopener">
  ▶ Watch on YouTube
</a>

{% if session.slides %}
<a href="{{ session.slides }}" 
   target="_blank"
   rel="noopener">
  📄 Slides
</a>
{% endif %}

<a href="{{ session.url | relative_url }}">
  ℹ Session details
</a>

</div>

</div>

</div>

  {% endif %}
{% endfor %}

</section>


<h2 style="text-align:center; margin-top:5rem;">
  Slides
</h2>

<p class="description">
These sessions do not have a recording available, but the presentation slides are available to view.
</p>


<section class="recordings-grid">

{% for session in site.programme-days-2026 %}
  {% if session.slides and session.recording == nil %}

<div class="recording-card">

<div class="recording-content">

<div class="badge">
{{ session.category | capitalize }}
</div>

<div class="recording-title">
{{ session.title }}
</div>

<div class="meta">
{% if session.speaker %}
<strong>Speakers:</strong><br>
{{ session.speaker }}
{% endif %}
</div>


<div class="meta">
{% if session.contributor %}
<strong>Speakers:</strong><br>
{{ session.contributor }}
{% endif %}
</div>


<div class="recording-buttons">

<a href="{{ session.slides }}" 
   target="_blank"
   rel="noopener">
  📄 View slides
</a>

<a href="{{ session.url | relative_url }}">
  ℹ Session details
</a>

</div>

</div>

</div>

  {% endif %}
{% endfor %}

</section>