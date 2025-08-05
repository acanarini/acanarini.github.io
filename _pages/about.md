---
title: "About"
layout: gridlay
permalink: /about/
---

## About Our Lab

{% for member in site.data.pi %}
<div class="member-card">
  <img src="/assets/images/{{ member.photo }}" alt="{{ member.name }}" class="profile-pic"/>
  <div class="member-info">
    <h3>{{ member.name }}</h3>
    <p><i>{{ member.info }}</i></p>
    {% if member.email %}<p><a href="mailto:{{ member.email }}">{{ member.email }}</a></p>{% endif %}
    <ul>
      {% for i in (1..member.number_educ | plus: 0) %}
        {% assign key = "education" | append: i %}
        {% if member[key] %}<li>{{ member[key] }}</li>{% endif %}
      {% endfor %}
    </ul>
  </div>
</div>
{% endfor %}

{% if site.data.grants %}
### Grants
<ul>
{% for grant in site.data.grants %}
  <li>{{ grant.name }}</li>
{% endfor %}
</ul>
{% endif %}

{% if site.data.awards %}
### Awards
<ul>
{% for award in site.data.awards %}
  <li>{{ award.name }}</li>
{% endfor %}
</ul>
{% endif %}

### Sponsors
<div class="sponsor-logos">
{% for funder in site.data.funders %}
  {% if funder.url %}
    <a href="{{ funder.url }}" target="_blank"><img src="/assets/images/{{ funder.image }}" alt="funder logo"/></a>
  {% else %}
    <img src="/assets/images/{{ funder.image }}" alt="funder logo"/>
  {% endif %}
{% endfor %}
</div>
