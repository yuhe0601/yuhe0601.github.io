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
  <div style="
  border: 1px solid #e0e0e0;
  border-radius: 10px;
  padding: 15px 18px;
  background: #ffffff;
  box-shadow: 0 2px 6px rgba(0,0,0,0.05);
  transition: all 0.2s ease;
"
onmouseover="this.style.boxShadow='0 4px 12px rgba(0,0,0,0.1)'"
onmouseout="this.style.boxShadow='0 2px 6px rgba(0,0,0,0.05)'"
>
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

      <!-- Title -->
      <div class="title">{{ project.title }}</div>

      <!-- Authors -->
      {% if project.authors %}
      <div class="author">
        {{ project.authors | replace: "Yuhe Zhang", "<strong>Yuhe Zhang</strong>" }}
      </div>
      {% endif %}

      <!-- Description -->
      <div class="periodical">
        {{ project.description }}
      </div>

      <!-- ⭐ 项目信息（这里是你之前缺的关键部分） -->
      <div class="periodical" style="font-size: 0.95em; color: #555;">
        {% if project.period %}
          <div><strong>Period:</strong> {{ project.period }}</div>
        {% endif %}
        {% if project.source %}
          <div><strong>Source:</strong> {{ project.source }}</div>
        {% endif %}
        {% if project.funding %}
          <div><strong>Funding:</strong> {{ project.funding }}</div>
        {% endif %}
        {% if project.role %}
          <div><strong>Role:</strong> {{ project.role }}</div>
        {% endif %}
      </div>

      <!-- Links -->
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
