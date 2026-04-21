---
layout: page
title: Projects
permalink: /projects/
description: A growing collection of your cool projects.
nav: true
nav_order: 3
---

<ul>
{% assign sorted_projects = site.projects | sort: "importance" %}
{% for project in sorted_projects %}
  <li>
    <strong>{{ project.title }}</strong><br>
    {{ project.description }}<br>

    {% if project.link %}
      <a href="{{ project.link }}">[Project Link]</a>
    {% endif %}

    {% if project.github %}
      <a href="{{ project.github }}">[GitHub]</a>
    {% endif %}
  </li>
  <br>
{% endfor %}
</ul>
