---
layout: splash
title:  "Past Durham HPC Days"
permalink: /past/
classes: [full-programme]
---

<style>

body {
  font-family: 'Inter', sans-serif;
  scroll-behavior: smooth;
}
section {
  max-width: 900px;
  margin: 3rem auto;
  padding: 0 1.5rem;
  text-align: center;
}
h3 {
  font-weight: 600;
  color: #002A41;
}

h1 {
  font-weight: 600;
  color: #002A41;
  font-size: 2.5rem;
}

h2 {
  font-weight: 600;
  color: #002A41;
  font-size: 2.2rem;
}


p, t {
  font-size: 1.1rem;
  line-height: 1.7;
  color: #002A41;
}
.btn {
  background: #002A41;
  color: #fff !important;
  padding: 0.8rem 1.6rem;
  border-radius: 30px;
  font-weight: 500;
  text-decoration: none;
  transition: 0.3s ease;
}
.btn:hover {
  background: #003d80;
  transform: translateY(-3px);
}

/* Image grid */
.image-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1rem;
  margin-top: 1rem;
}
.image-grid img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  border-radius: 12px;
  transition: transform 0.4s ease, box-shadow 0.4s ease;
}
.image-grid img:hover {
  transform: scale(1.05);
  box-shadow: 0 8px 16px rgba(0,0,0,0.25);
}

/* Fade-in animations */
.fade-in {
  opacity: 0;
  transform: translateY(40px);
  transition: all 0.8s ease-out;
}
.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Callout box (for links) */
.callout {
  background: #002A41;
  color: white;
  padding: 1.2rem;
  margin: 1.2rem auto;
  border-radius: 12px;
  max-width: 700px;
}
.callout a {
  color: #fff;
  text-decoration: underline;
  font-weight: 600;
}

.callout:hover {
  background: #003d80;
  transform: translateY(-3px);
}


</style>


<section class="fade-in">
  <h1>Past Durham HPC Days</h1>
  <p>
    Explore previous editions of <strong>Durham HPC Days</strong>, including highlights, photos,and links to full programmes and documentation.
  </p>
</section>


<section class="fade-in">
  <h2>🖥️ Durham HPC Days 2025</h2>

  <div class="callout">
    <strong>Full Programme:</strong><br>
    <a href="https://durham.readthedocs.io/en/latest/hpcdays2025/index.html" target="_blank">
      Visit the 2025 Website →
    </a>
  </div>

  <p>
    The <strong>2025 edition</strong> focused on advanced GPU programming, large-scale
    parallel optimisation, hands-on profiling, and modern HPC workflows.
    Researchers, RSEs, and developers from multiple scientific fields participated in
    sessions, tutorials, and collaborative discussions.
  </p>

  <div class="image-grid">
    <img src="https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/social.png?raw=true" alt="HPC Days 2025 Photo 1">
    <img src="https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/stickers.jpg?raw=true" alt="HPC Days 2025 Photo 2">
    <img src="https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/food-truck.jpg?raw=true" alt="HPC Days 2025 Photo 3">
  </div>
</section>


<section class="fade-in">
  <h2>🖥️ Durham HPC Days 2024</h2>

  <div class="callout">
    <strong>Full Programme:</strong><br>
    <a href="https://scicomp.webspace.durham.ac.uk/events/code_performance_series/durham-hpc-days-2024/" target="_blank">
      Visit the 2024 Website →
    </a>
  </div>

  <p>
    The <strong>2024 event</strong> focused on the evolving demands faced by compute centres and research computing groups. Core topics included: talent scarcity, scalability and performance limitations,energy consumption and Net-Zero computing and traditional simulation communities and ML/AI workflows
  </p>

  <div class="image-grid">
    <img src="https://scicomp.webspace.durham.ac.uk/wp-content/uploads/sites/219/2024/05/hpc-days-1208x906.jpg" alt="HPC Days 2024 Photo 1">
  </div>
</section>




<section class="fade-in">
  <h2>🖥️ Durham HPC Days 2023</h2>

  <div class="callout">
    <strong>Full Programme:</strong><br>
    <a href="https://tobiasweinzierl.webspace.durham.ac.uk/research/workshops/durham-hpc-days-spring-2023/" target="_blank">
      Visit the 2023 Website →
    </a>
  </div>

  <p>
    The <strong>2023 event</strong> focused on exploring the community’s transition from homogeneous to increasingly heterogeneous supercomputing architectures, focusing on how to adapt algorithms, workflows and quantities of interest to new hardware; the role of performance portability; lessons learned from prototype and experimental systems within ExCALIBUR and the integration of core computer science and applied mathematics with domain sciences.
  </p>

  <div class="image-grid">
    <img src="https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/hpc-days-2023-2.jpg?raw=true" alt="HPC Days 2023 Photo 1">
    <img src="https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/hpc-days-2023-1.jpg?raw=true" alt="HPC Days 2023 Photo 2">
  </div>
  
</section>





<section class="fade-in">
  <h2>📈 Looking Forward</h2>
  <p>
    Durham HPC Days continues to grow each year, expanding into new areas such as
    sustainable HPC, AI-accelerated workflows, and advanced research software engineering.
  </p>
  <a href="{{ site.baseurl }}/" class="btn">Back to Home</a>
</section>

<script>
(function() {
  function onScroll() {
    document.querySelectorAll('.fade-in').forEach(el => {
      var rect = el.getBoundingClientRect();
      if (rect.top < window.innerHeight - 100) el.classList.add('visible');
    });
  }
  document.addEventListener('scroll', onScroll);
  document.addEventListener('DOMContentLoaded', onScroll);
})();
</script>
