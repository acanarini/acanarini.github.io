---
title: "outreach"
layout: gridlay
sitemap: false
permalink: /outreach/
---

<style>
.btn{
    margin-bottom:5px;
    padding-top:1px;
    padding-bottom:1px;
    padding-left:15px;
    padding-right:15px;
}
.jumbotron{
    padding:3%;
    padding-bottom:10px;
    padding-top:10px;
    margin-top:10px;
    margin-bottom:30px;
}
</style>

## Conference

{% assign conferenceList = false %}
{% assign organizedList = false %}
{% for publi in site.data.conference %}
  {% if publi.type contains "conference" %}
    {% assign conferenceList = true %}
  {% endif %}
  {% if publi.type contains "organized" %}
    {% assign organizedList = true %}
  {% endif %}
{% endfor %}

{% if conferenceList == true %}
<div class="jumbotron">
### Selected presentations

<ul>
  {% for publi in site.data.conference %}
    {% if publi.type contains "conference" %}
      <li>{{ publi.name | replace: "-", "&#8211;" }} {% if publi.talk %}<i>{{ publi.talk }}</i>{% endif %}</li>
    {% endif %}
  {% endfor %}
</ul>
</div>
{% endif %}

{% if organizedList == true %}
<div class="jumbotron">
### Conference organization
<ul>
  {% for publi in site.data.conference %}
    {% if publi.type contains "organized" %}
      <li>{{ publi.name | replace: "-", "&#8211;" }} {% if publi.talk %}<i>{{ publi.talk }}</i>{% endif %}</li>
    {% endif %}
  {% endfor %}
</ul>
</div>
{% endif %}

