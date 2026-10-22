---
layout: default
title: Attendee Information
permalink: /attendee-information/
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
    justify-content: flex-start;
    overflow: hidden;
  }

  .ws-hero__overlay {
    position: absolute;
    inset: 0;
background:
  linear-gradient(
    rgba(0,42,65,0.92),
    rgba(0,42,65,0.92)
  );
    }


  .ws-hero__grid {
    position: absolute;
    inset: 0;
    background-image:
   linear-gradient(rgba(255, 220, 120, 0.06) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 220, 120, 0.06) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
  }

  .ws-hero__content {
    position: relative;
    z-index: 2;
    padding: 0 3rem 3rem;
    max-width: 860px;
  }

  .ws-hero__eyebrow {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.65);
    margin-bottom: 0.75rem;
  }

  .ws-hero__eyebrow::before {
    content: '';
    display: block;
    width: 28px;
    height: 2px;
  background: #ffffff;
    border-radius: 2px;
  }

  .ws-hero h1 {
    
    font-size: clamp(2.4rem, 5vw, 4rem);
    font-weight: 400;
    color: #ffffff;
    margin: 0 0 0.5rem;
    line-height: 1.08;
    letter-spacing: -0.02em;
  }

  .ws-hero h1 em {
    font-style: italic;
    color: #7ec8ff;
  }

  .ws-hero__sub {
    font-size: 1rem;
    color: rgba(255,255,255,0.60);
    font-weight: 300;
    margin: 0;
    letter-spacing: 0.01em;
  }
  
  @media(max-width:768px){

.ws-hero{
height:35vh;
align-items:center;
text-align:center;
}

.ws-hero__content{
padding:0 1.5rem;
}

.ws-hero__eyebrow{
display:none;
}

}

.section-content {
  max-width:1200px;
  margin:auto;
  padding:3rem 2rem;
}

.info-card {
  background:white;
  padding:2rem;
  margin-bottom:2rem;
  border-left:6px solid #68246D;
  border-radius:12px;
  box-shadow:0 10px 25px rgba(0,0,0,0.08);
}

.info-card h2 {
  margin-top:0;
}

.checklist {
  list-style:none;
  padding:0;
}

.checklist li {
  padding-left:1.6rem;
  position:relative;
  margin-bottom:0.7rem;
}

.checklist li::before {
  content:"✓";
  position:absolute;
  left:0;
  color:#68246D;
  font-weight:bold;
}

@media(max-width:768px){
  .parallax-hero{
    height:30vh;
    background-attachment:scroll;
    background-position:center;
  }

  .parallax-hero h1{
    font-size:2.3rem;
  }

  .info-card{
    padding:1.5rem;
  }
}
</style>


<section class="ws-hero">

<div class="ws-hero__grid"></div>

<div class="ws-hero__content">

<p class="ws-hero__eyebrow">
Durham HPC Days 2026
</p>

<h1>Attendee Information</h1>

<p class="ws-hero__sub">
Everything you need before arriving at HPC Days 2026
</p>

</div>
</section>

<section class="section-content">



<!-- REGISTRATION -->
<div class="info-card">
  <h2>Registration Desk</h2>

  <p>
    Registration will take place at the:
  </p>
  
  <p>
<strong>Mountjoy Centre Event Space</strong><br>
Stockton Rd<br>
Durham City<br>
Durham DH1 3UP
</p>



  <ul class="checklist">
    <li>Please register on arrival before attending any sessions</li>
  </ul>
</div>




<!-- VENUES -->
<div class="info-card">
  <h2>Event Venues</h2>

  <p>
    Sessions will take place across three locations within Durham University:
  </p>

  <ul class="checklist">
    <li><strong>Mathematical Science and Computer Science Building (MCS) </strong> - main lectures and sessions</li>
    <li><strong>Rowan House (RH)</strong> - selected sessions and activities</li>
    <li><strong>Mountjoy Centre (MJC)</strong> - registration, catering, and additional sessions</li>
  </ul>

  <p>
    All three venues are located within a <strong>5-minute walking distance</strong> of each other on campus.
    Please refer to the  <a href="https://hpc-days.github.io/Durham-HPC-Days-2026/rooms/">Conference Rooms Map</a> for routes and building entrances.
  </p>

<p>
  A <strong>Quiet Room</strong> will be available throughout the conference in <strong>MCS 2053</strong>. This space is intended for attendees who would like a quiet place to work, or simply take a break from the conference. Please help us keep the room quiet by taking phone calls, online meetings, and conversations elsewhere.
</p>

<p>
  A <strong>Multi-Faith Room</strong> will be available throughout the conference in <strong>MJC 4004</strong>. Please be respectful of others using the room and help maintain a peaceful environment.
</p>

  <p>
    We recommend checking the programme each day to confirm the correct venue for your sessions.
  </p>
</div>



<!-- PARKING -->
<div class="info-card">
  <h2>Parking</h2>

  <p>
    Limited parking is available on campus near the event buildings.
    To request a parking space, please complete the parking request form in advance.
  </p>

  <ul class="checklist">
    <li>Parking is allocated on a first-come, first-served basis</li>
    <li>Spaces are limited and cannot be guaranteed without a request</li>
    <li>Further instructions will be provided after approval</li>
  </ul>

  <p>
  
   <a href="https://forms.office.com/e/YKinMEAxBX">Parking request form</a>

  </p>
</div>

<!-- TRAVEL -->
<div class="info-card">
  <h2>Travel</h2>

  <p>
    The University’s official
    <a href="https://www.durham.ac.uk/visit-us/">Visit Us page</a>
    provides some general guidance. Below are additional notes on how to reach the venue.
  </p>

  <h3>From Newcastle International Airport</h3>
  <ul class="checklist">
    <li>
      Take the Metro (there is only one line) to Newcastle Central Station
      (less than 40 minutes), then take a train south to Durham.
      Durham is approximately 15 minutes from Newcastle by train.
    </li>

    <li>
      Alternatively, you can take a taxi directly from the airport
      (around £60, approximately 40 minutes).
    </li>
  </ul>

  <h3>From Durham Train Station</h3>
  <ul class="checklist">
    <li>
      The venue is a 30–40 minute walk from Durham station.
    </li>

    <li>
      Taxis are usually available outside the station and cost approximately £10–15.
    </li>

    <li>
      There is a bus stop directly outside the station with two relevant services:
    </li>
  </ul>

  <h3>Local buses</h3>
  <ul class="checklist">
    <li>
      <strong>Bus 42 to Mount Oswald</strong> - runs approximately every 30 minutes.
      Get off at “South Road Colleges”, then walk up the hill (around 5 minutes).
    </li>

    <li>
      <strong>Bus 41 to University Science Park</strong> - get off at the final stop.
    </li>
  </ul>
</div>


<!-- ACCOMMODATION -->
<div class="info-card">
  <h2>Accommodation</h2>

  <p>
    Accommodation is not provided. Attendees should book independently.
  </p>

  <ul class="checklist">
    <li><a href="https://durham.hotelindigo.com/">Hotel Indigo</a></li>
    <li><a href="https://www.premierinn.com/gb/en/hotels/england/county-durham/durham/durham-city-centre-walkergate.html">Premier Inn Durham City Centre</a></li>
    <li><a href="https://www.marriott.com">Durham Marriott Hotel</a></li>
    <li><a href="https://www.travelodge.co.uk/hotels/204/Durham-hotel">Travelodge Durham</a></li>
  </ul>
<p>
As it is graduation week in Durham, hotel spaces may be in short supply.  However Newcastle is only 11 minutes away from Durham by train, with regular and frequent services, and plenty of city centre hotels.
</p>

</div>


<!-- CATERING -->
<div class="info-card">
  <h2>Catering</h2>

  <ul class="checklist">
    <li>Lunch will be provided Monday to Friday</li>
    <li>Dinner will be provided Monday to Thursday</li>
    <li>Please ensure dietary requirements have been submitted in advance</li>
  </ul>
</div>


<!-- ACCESSIBILITY -->
<div class="info-card">
  <h2>Accessibility & Special Requirements</h2>

  <p>
    If you have any accessibility requirements or needs that were not
    included in the registration form, please contact the organisers
    as soon as possible so we can support you appropriately.
  </p>
  
  If you experience any issues receiving your Microsoft Teams invitation, problems registering for a session, or have questions about online participation, please get in touch with us and we will be happy to help.

<br>

📧 Contact: <a href="mailto:YOUR_EMAIL_HERE">eva.fernandez-amez@durham.ac.uk</a>
</div>



<div class="info-card">
  <h2>Code of Conduct</h2>

  <p>
     We are committed to providing a welcoming environment for all participants. All attendees, speakers, exhibitors,
    sponsors, volunteers, and organisers are expected to follow the event's
    Code of Conduct throughout the conference.
  </p>


    <p>
    Please read the full Code of Conduct here:
    <a href="https://www.cake.ac.uk/CAKEbox/code-of-conduct/"
       target="_blank"
       rel="noopener noreferrer">
      CAKE Code of Conduct
    </a>.
  </p>

  <p>
    If you experience or witness behaviour that violates the Code of Conduct,
    please contact a member of the organising team. Reports may also be made
    directly to the CAKE team using the contact information provided on the
    Code of Conduct page.
  </p>

</div>




</section>
