---
title: "Team"
layout: gridlay
sitemap: false
permalink: /team/
---

## Team

 **We are  looking for new team members** [(see openings)]({{ site.url }}{{ site.baseurl }}/opportunities) **!**

<div class="team-photo-carousel" id="team-photo-carousel" aria-label="MICSO Lab team photographs" aria-roledescription="carousel">
  <div class="team-carousel-stage">
    <figure class="team-carousel-slide is-active" aria-hidden="false">
      <img src="{{ site.url }}{{ site.baseurl }}/images/Team_2025.jpg" alt="MICSO Lab team in 2025">
      <figcaption>MICSO Lab team, 2025</figcaption>
    </figure>
    <figure class="team-carousel-slide" aria-hidden="true">
      <img src="{{ site.url }}{{ site.baseurl }}/images/team-carousel/malga-coot-2026.jpg" alt="MICSO Lab field team at Malga Coot in 2026">
      <figcaption>Malga Coot, 2026</figcaption>
    </figure>
    <figure class="team-carousel-slide" aria-hidden="true">
      <img src="{{ site.url }}{{ site.baseurl }}/images/team-carousel/passo-gavia-2026.jpg" alt="MICSO Lab field team at Passo Gavia in 2026">
      <figcaption>Passo Gavia, 2026</figcaption>
    </figure>
    <figure class="team-carousel-slide" aria-hidden="true">
      <img src="{{ site.url }}{{ site.baseurl }}/images/team-carousel/team-building-2026.jpg" alt="MICSO Lab at a team-building event in 2026">
      <figcaption>Team building, 2026</figcaption>
    </figure>

    <button class="team-carousel-control team-carousel-previous" type="button" aria-label="Previous team photograph">&#10094;</button>
    <button class="team-carousel-control team-carousel-next" type="button" aria-label="Next team photograph">&#10095;</button>
  </div>

  <div class="team-carousel-dots" aria-label="Choose a team photograph">
    <button class="is-active" type="button" aria-label="Show photograph 1" aria-current="true"></button>
    <button type="button" aria-label="Show photograph 2"></button>
    <button type="button" aria-label="Show photograph 3"></button>
    <button type="button" aria-label="Show photograph 4"></button>
  </div>
</div>

<style>
.team-photo-carousel {
  width: 100%;
  max-width: 1000px;
  margin: 0 auto 2rem;
}

.team-carousel-stage {
  position: relative;
  aspect-ratio: 4 / 3;
  overflow: hidden;
  background: #f2f2f2;
  border-radius: 4px;
}

.team-carousel-slide {
  position: absolute;
  inset: 0;
  margin: 0;
  opacity: 0;
  transition: opacity 0.65s ease;
  pointer-events: none;
}

.team-carousel-slide.is-active {
  opacity: 1;
  pointer-events: auto;
}

.team-carousel-slide img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.team-carousel-slide figcaption {
  position: absolute;
  right: 0;
  bottom: 0;
  left: 0;
  padding: 0.55rem 1rem;
  color: #fff;
  background: rgba(0, 0, 0, 0.58);
  text-align: center;
}

.team-carousel-control {
  position: absolute;
  z-index: 2;
  top: 50%;
  width: 44px;
  height: 56px;
  padding: 0;
  border: 0;
  color: #fff;
  background: rgba(0, 0, 0, 0.42);
  font-size: 30px;
  line-height: 1;
  cursor: pointer;
  transform: translateY(-50%);
}

.team-carousel-control:hover,
.team-carousel-control:focus {
  background: rgba(0, 0, 0, 0.68);
  outline: 2px solid #fff;
  outline-offset: -4px;
}

.team-carousel-previous { left: 0; }
.team-carousel-next { right: 0; }

.team-carousel-dots {
  display: flex;
  justify-content: center;
  gap: 8px;
  margin-top: 10px;
}

.team-carousel-dots button {
  width: 11px;
  height: 11px;
  padding: 0;
  border: 0;
  border-radius: 50%;
  background: #b7b7b7;
  cursor: pointer;
}

.team-carousel-dots button.is-active {
  background: #337ab7;
}

@media (max-width: 576px) {
  .team-carousel-control {
    width: 38px;
    height: 48px;
    font-size: 25px;
  }

  .team-carousel-slide figcaption {
    font-size: 13px;
  }
}

@media (prefers-reduced-motion: reduce) {
  .team-carousel-slide {
    transition: none;
  }
}
</style>

<script>
(function () {
  var carousel = document.getElementById("team-photo-carousel");
  if (!carousel) return;

  var slides = Array.prototype.slice.call(carousel.querySelectorAll(".team-carousel-slide"));
  var dots = Array.prototype.slice.call(carousel.querySelectorAll(".team-carousel-dots button"));
  var previous = carousel.querySelector(".team-carousel-previous");
  var next = carousel.querySelector(".team-carousel-next");
  var current = 0;
  var timer = null;
  var reduceMotion = window.matchMedia && window.matchMedia("(prefers-reduced-motion: reduce)").matches;

  function show(index) {
    current = (index + slides.length) % slides.length;
    slides.forEach(function (slide, i) {
      var active = i === current;
      slide.classList.toggle("is-active", active);
      slide.setAttribute("aria-hidden", active ? "false" : "true");
      dots[i].classList.toggle("is-active", active);
      dots[i].setAttribute("aria-current", active ? "true" : "false");
    });
  }

  function stop() {
    if (timer) {
      window.clearInterval(timer);
      timer = null;
    }
  }

  function start() {
    stop();
    if (!reduceMotion) {
      timer = window.setInterval(function () { show(current + 1); }, 5000);
    }
  }

  previous.addEventListener("click", function () { show(current - 1); start(); });
  next.addEventListener("click", function () { show(current + 1); start(); });
  dots.forEach(function (dot, i) {
    dot.addEventListener("click", function () { show(i); start(); });
  });

  carousel.addEventListener("mouseenter", stop);
  carousel.addEventListener("mouseleave", start);
  carousel.addEventListener("focusin", stop);
  carousel.addEventListener("focusout", start);
  document.addEventListener("visibilitychange", function () {
    if (document.hidden) stop();
    else start();
  });

  start();
}());
</script>


## PI

{% for member in site.data.pi %}
<div class="jumbotron">
<div class="row">
<div class="col-sm-4">
  <img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-8 col-xs-12">
  <h3>{{ member.name }}</h3>
  <i>{{ member.info }}</i><br>
  {% if member.email %}<a href="mailto:{{ member.email }}" target="_blank"><i class="fa fa-envelope-square fa-3x"></i></a> {% endif %}
  {% if member.cv %} <a href="{{ site.url }}{{ site.baseurl }}/cv/{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-3x"></i></a> {% endif %}
  {% if member.scholar %} <a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-3x"></i></a> {% endif %}
  {% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-3x"></i></a> {% endif %}
  {% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-3x"></i></a> {% endif %}
  {% if member.orcid %}<a href="https://orcid.org/{{ member.orcid }}" target="_blank" title="ORCID"><i class="ai ai-orcid-square ai-3x"></i></a>{% endif %}

  <ul style="overflow: hidden;margin-left: -25px;">
  {% if member.number_educ == 1 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 2 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 3 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 4 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 5 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 6 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education6 | replace: "-","&#8211;"}} </li>
  {% endif %}
  </ul>
</div>
</div>
</div>
{% endfor %}






## Postdocs


{% for member in site.data.post_docs %}
<div class="jumbotron">
<div class="row">
<div class="col-sm-4">
  <img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-8 col-xs-12">
  <h3>{{ member.name }}</h3>
  <i>{{ member.info }}</i><br>
  <div class="profile-links">
  {% if member.email %}<a href="mailto:{{ member.email }}"><i class="fa fa-envelope-square fa-3x"></i></a>{% endif %}
  {% if member.cv %}<a href="{{ site.url }}{{ site.baseurl }}/cv/{{ member.cv }}"><i class="ai ai-cv-square ai-3x"></i></a>{% endif %}
  {% if member.scholar %}<a href="{{ member.scholar }}"><i class="ai ai-google-scholar-square ai-3x"></i></a>{% endif %}
  {% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-3x"></i></a> {% endif %}
  {% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-3x"></i></a> {% endif %}
  {% if member.orcid %}<a href="https://orcid.org/{{ member.orcid }}" target="_blank" title="ORCID"><i class="ai ai-orcid-square ai-3x"></i></a>{% endif %}
  {% if member.website %}<a href="{{ member.website }}" target="_blank" title="Personal website"><i class="fa fa-globe fa-3x"></i></a>{% endif %}
</div> 
<ul style="overflow: hidden;margin-left: -25px;">
  {% if member.number_educ == 1 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 2 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 3 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 4 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 5 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 6 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education6 | replace: "-","&#8211;"}} </li>
  {% endif %}
  </ul>
</div>
</div>
</div>
{% endfor %}





## PhD students

{% for member in site.data.phd %}
<div class="jumbotron">
<div class="row">
<div class="col-sm-4">
  <img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-8 col-xs-12">
  <h3>{{ member.name }}</h3>
  <i>{{ member.info }}</i><br>
  <div class="profile-links">
  {% if member.email %}<a href="mailto:{{ member.email }}"><i class="fa fa-envelope-square fa-3x"></i></a>{% endif %}
  {% if member.cv %}<a href="{{ site.url }}{{ site.baseurl }}/cv/{{ member.cv }}"><i class="ai ai-cv-square ai-3x"></i></a>{% endif %}
  {% if member.scholar %}<a href="{{ member.scholar }}"><i class="ai ai-google-scholar-square ai-3x"></i></a>{% endif %}
  {% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-3x"></i></a> {% endif %}
  {% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-3x"></i></a> {% endif %}
  {% if member.orcid %}<a href="https://orcid.org/{{ member.orcid }}" target="_blank" title="ORCID"><i class="ai ai-orcid-square ai-3x"></i></a>{% endif %}
  {% if member.website %}<a href="{{ member.website }}" target="_blank" title="Personal website"><i class="fa fa-globe fa-3x"></i></a>{% endif %}
</div> 
<ul style="overflow: hidden;margin-left: -25px;">
  {% if member.number_educ == 1 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 2 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 3 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 4 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 5 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 6 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education6 | replace: "-","&#8211;"}} </li>
  {% endif %}
  </ul>
</div>
</div>
</div>
{% endfor %}

## Thesis students

{% for member in site.data.thesis %}
<div class="jumbotron">
<div class="row">
<div class="col-sm-4">
  <img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-8 col-xs-12">
  <h3>{{ member.name }}</h3>
  <i>{{ member.info }}</i><br>
  <div class="profile-links">
  {% if member.email %}<a href="mailto:{{ member.email }}"><i class="fa fa-envelope-square fa-3x"></i></a>{% endif %}
  {% if member.cv %}<a href="{{ site.url }}{{ site.baseurl }}/cv/{{ member.cv }}"><i class="ai ai-cv-square ai-3x"></i></a>{% endif %}
  {% if member.scholar %}<a href="{{ member.scholar }}"><i class="ai ai-google-scholar-square ai-3x"></i></a>{% endif %}
  {% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-3x"></i></a> {% endif %}
  {% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-3x"></i></a> {% endif %}
  {% if member.orcid %}<a href="https://orcid.org/{{ member.orcid }}" target="_blank" title="ORCID"><i class="ai ai-orcid-square ai-3x"></i></a>{% endif %}
  {% if member.website %}<a href="{{ member.website }}" target="_blank" title="Personal website"><i class="fa fa-globe fa-3x"></i></a>{% endif %}
</div> 
<ul style="overflow: hidden;margin-left: -25px;">
  {% if member.number_educ == 1 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 2 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 3 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 4 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 5 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 6 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education6 | replace: "-","&#8211;"}} </li>
  {% endif %}
  </ul>
</div>
</div>
</div>
{% endfor %}



## Current Visiting Scholar

{% for member in site.data.visiting %}
<div class="jumbotron">
<div class="row">
{% if member.photo %}
<div class="col-sm-4">
  <img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-8 col-xs-12">
{% else %}
<div class="col-sm-12 col-xs-12">
{% endif %}
  <h3>{{ member.name }}</h3>
  <i>{{ member.info }}</i><br>
  <div class="profile-links">
  {% if member.email %}<a href="mailto:{{ member.email }}"><i class="fa fa-envelope-square fa-3x"></i></a>{% endif %}
  {% if member.cv %}<a href="{{ site.url }}{{ site.baseurl }}/cv/{{ member.cv }}"><i class="ai ai-cv-square ai-3x"></i></a>{% endif %}
  {% if member.scholar %}<a href="{{ member.scholar }}"><i class="ai ai-google-scholar-square ai-3x"></i></a>{% endif %}
  {% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-3x"></i></a> {% endif %}
  {% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-3x"></i></a> {% endif %}
  {% if member.orcid %}<a href="https://orcid.org/{{ member.orcid }}" target="_blank" title="ORCID"><i class="ai ai-orcid-square ai-3x"></i></a>{% endif %}
  {% if member.website %}<a href="{{ member.website }}" target="_blank" title="Personal website"><i class="fa fa-globe fa-3x"></i></a>{% endif %}
</div> 
<ul style="overflow: hidden;margin-left: -25px;">
  {% if member.number_educ == 1 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 2 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 3 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 4 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 5 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 6 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education6 | replace: "-","&#8211;"}} </li>
  {% endif %}
  </ul>
</div>
</div>
</div>
{% endfor %}










## Alumni

<div class="jumbotron">
{% assign number_printed = 0 %}
{% for member in site.data.alumni %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}


<div class="col-sm-4 col-xs-12">
  <h4>{{ member.name }}</h4>
  <i>{{ member.duration }} <br> Role: {{ member.info }}</i>
  <ul style="overflow: hidden">
  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}
</div>




