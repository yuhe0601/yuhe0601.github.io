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

<!-- ⭐ Selected Projects -->
{% assign selected_projects = all_projects | where: "selected", true | sort: "importance" %}
{% if selected_projects.size > 0 %}
<h2>Selected Projects</h2>
<ol class="bibliography">
{% for project in selected_projects %}
  <li>
    <div class="title">{{ project.title }}</div>

    {% if project.authors %}
    <div class="author">
      {{ project.authors | replace: "Yuhe Zhang", "<strong>Yuhe Zhang</strong>" }}
    </div>
    {% endif %}

    <div class="periodical">{{ project.description }}</div>

    <div class="links">
      {% if project.github %}<a href="{{ project.github }}">[code]</a>{% endif %}
      {% if project.link %}<a href="{{ project.link }}">[project]</a>{% endif %}
      {% if project.paper %}<a href="{{ project.paper }}">[paper]</a>{% endif %}
      {% if project.video %}<a href="{{ project.video }}">[video]</a>{% endif %}
    </div>
  </li>
{% endfor %}
</ol>
{% endif %}

<!-- ⭐ 按年份分组 -->
{% assign projects_by_year = all_projects | group_by: "year" | sort: "name" | reverse %}

{% for year in projects_by_year %}
  <h2>{{ year.name }}</h2>
  <ol class="bibliography">
  {% assign year_projects = year.items | sort: "importance" %}
  {% for project in year_projects %}
    {% unless project.selected %}
    <li>
      <div class="title">{{ project.title }}</div>

      {% if project.authors %}
      <div class="author">
        {{ project.authors | replace: "Yuhe Zhang", "<strong>Yuhe Zhang</strong>" }}
      </div>
      {% endif %}

      <div class="periodical">{{ project.description }}</div>

      <div class="links">
        {% if project.github %}<a href="{{ project.github }}">[code]</a>{% endif %}
        {% if project.link %}<a href="{{ project.link }}">[project]</a>{% endif %}
        {% if project.paper %}<a href="{{ project.paper }}">[paper]</a>{% endif %}
        {% if project.video %}<a href="{{ project.video }}">[video]</a>{% endif %}
      </div>
    </li>
    {% endunless %}
  {% endfor %}
  </ol>
{% endfor %}

</div>
