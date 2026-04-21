---
layout: page
title: Projects
permalink: /projects/
description: These are my research projects and ongoing work.
nav: true
nav_order: 3
---

<div class="publications">

{% assign all_projects = site.projects %}
{% assign projects_by_year = all_projects | group_by: "year" | sort: "name" | reverse %}

{% for year in projects_by_year %}

  <h2>{{ year.name }}</h2>

  {% assign year_projects = year.items | sort: "importance" %}

  {% for project in year_projects %}

  <div style="
    border: 1px solid #e0e0e0;
    border-radius: 10px;
    padding: 15px 18px;
    background: #ffffff;
    box-shadow: 0 2px 6px rgba(0,0,0,0.05);
    margin-bottom: 18px;
    transition: all 0.2s ease;
  "
  onmouseover="this.style.boxShadow='0 4px 12px rgba(0,0,0,0.1)'"
  onmouseout="this.style.boxShadow='0 2px 6px rgba(0,0,0,0.05)'"
  >

    <!-- Source -->
    {% if project.source %}
    <div style="font-size: 0.85em; color: #888;">
      <em>{{ project.source }}</em>
    </div>
    {% endif %}

    <!-- Title -->
    <div class="title" style="font-size: 1.1em; margin-top: 4px;">
      {{ project.title }}
    </div>

    <!-- Authors（可选） -->
    {% if project.authors %}
    <div class="author">
      {{ project.authors | replace: "Yuhe Zhang", "<strong>Yuhe Zhang</strong>" }}
    </div>
    {% endif %}

    <!-- ⭐ Info（Grant Number 放最前） -->
    <div style="font-size: 0.95em; color: #555; margin-top: 6px;">

      {% if project.grant_number %}
        <div><strong>Grant Number:</strong> {{ project.grant_number }}</div>
      {% endif %}

      {% if project.period %}
        <div><strong>Period:</strong> {{ project.period }}</div>
      {% endif %}

      {% if project.funding %}
        <div><strong>Funding:</strong> {{ project.funding }}</div>
      {% endif %}

      {% if project.role %}
        <div><strong>Role:</strong> {{ project.role }}</div>
      {% endif %}

    </div>

    <!-- Description -->
    {% if project.description %}
    <div style="font-size: 0.9em; color: #555; margin-top: 8px;">
      {{ project.description }}
    </div>
    {% endif %}

    <!-- Links -->
    <div class="links" style="margin-top: 8px;">
      {% if project.github %}<a href="{{ project.github }}">[code]</a>{% endif %}
      {% if project.link %}<a href="{{ project.link }}">[project]</a>{% endif %}
      {% if project.paper %}<a href="{{ project.paper }}">[paper]</a>{% endif %}
      {% if project.video %}<a href="{{ project.video }}">[video]</a>{% endif %}
    </div>

  </div>

  {% endfor %}

{% endfor %}

</div>
