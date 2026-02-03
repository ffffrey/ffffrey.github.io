---
layout: page
title: research
permalink: /research/
description: 
nav: true
nav_order: 1
#display_categories: []
horizontal: false
---

In my research, I am broadly interested in theoretical biophysics and soft matter. 
Currently, my main focus is on the physics of fluid lipid membranes, with a focus on how geometry, mechanics, and self-assembly drive shape and topology changes in these soft biological interfaces. 
Using a combination of <strong>theoretical modeling and computer simulations</strong>, I study <strong>membrane remodeling</strong> across a range of biological systems.
 These include archaeal bolalipid membranes, endosomal membrane dynamics in plant cells, and processes of membrane turnover and growth. 
 Another central theme of my work is how proteins <strong>self-assemble</strong> into functional coats that generate forces and curvature, for example during <strong>clathrin-mediated endocytosis</strong>. 
 I also explore membrane interactions with <strong>viruses, nanoparticles, and cytoskeletal networks</strong>, addressing general physical principles that govern transport, remodeling, and organization in living matter. 
 Further details on these topics are provided below.

<!-- pages/projects.md -->
<div class="projects">
<!-- {% if site.enable_project_categories and page.display_categories %} -->
  <!-- Display categorized projects -->
  <!--{% for category in page.display_categories %}-->
  <h2 class="category">{{ category }}</h2>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
