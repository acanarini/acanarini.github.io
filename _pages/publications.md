---
title: "Publications"
layout: gridlay
sitemap: false
permalink: /publications/

---

<style>
code {padding: 6px 8px; font-size: 90%;}
</style>

# Publications

For a full list see <a href="###Refereed journal articles" class="text-info"> below</a> or go to <a href="https://scholar.google.com/citations?user=1NMOvPwAAAAJ&hl=en" class="text-info"> Google Scholar</a> , <a href="https://www.webofscience.com/wos/author/record/872543" class="text-info"> ResearcherID</a>

<style>
  .with-shadow {
    box-shadow: 5px 5px 10px #888888; /* Adjust the shadow values as needed */
  }
</style>


<style>
.jumbotron{
    padding:3%;
    padding-bottom:10px;
    padding-top:10px;
    margin-top:10px;
    margin-bottom:30px;
}
</style>

### Highlights

<div class="jumbotron">

{% assign number_printed = 0 %}
{% for publi in site.data.highlights %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="well">
  <script type="text/javascript" src="https://d1bxh8uas1mnw7.cloudfront.net/assets/embed.js"></script><div data-badge-popover="right" data-badge-type="donut" data-condensed="true" data-doi="{{ publi.doi }}" class="altmetric-embed" style="float: right; display: inline-block; clear: both;"></div>
  <pubtit>{{ publi.title }}</pubtit>
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive with-shadow" width="35%" style="float: left; margin-right: 15px;margin-top: 15px;" />
  <p>{{ publi.description }}</p>
  <p><em>{{ publi.authors }}</em></p>
  <p><strong><a href="{{ publi.link.url }}" class="text-info">{{ publi.link.display }}</a></strong></p>
  <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
  <p> {{ publi.news2 }}</p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<p> &nbsp; </p>
</div>


<style>
.jumbotron{
    padding:3%;
    padding-bottom:10px;
    padding-top:10px;
    margin-top:10px;
    margin-bottom:30px;
}
</style>


### Preprints

<div class="jumbotron">
{% bibliography --query @misc %}
</div>



### Refereed journal articles
<div class="jumbotron">
### 2023
{% bibliography --query @article[year =2023] %}
### 2022
{% bibliography --query @article[year =2022] %}
### 2021
{% bibliography --query @article[year =2021] %}
### 2020
{% bibliography --query @article[year =2020] %}
### 2019
{% bibliography --query @article[year =2019] %}
### 2018
{% bibliography --query @article[year =2018] %}
### 2017
{% bibliography --query @article[year =2017] %}
### 2016
{% bibliography --query @article[year =2016] %}
### 2015
{% bibliography --query @article[year =2015] %}
### 2010
{% bibliography --query @article[year =2010] %}
</div>


### Book Chapters and Editorials
<div class="jumbotron">
{% bibliography --query @incollection %}
</div>


