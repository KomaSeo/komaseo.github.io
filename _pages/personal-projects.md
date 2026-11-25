---
layout: page
title: Personal projects
permalink: /personal-projects/
description: Tools I built for myself and my friends. We implemented and used these tools for ourselves.
nav: false
---

<!-- Each card comes from a file in _projects/ (ordered by `importance`); clicking a card opens that file's page. -->
<!-- prettier-ignore-start -->
<div class="pp-grid">
{% assign pp_projects = site.projects | sort: "importance" %}
{% for project in pp_projects %}
<div class="pp-card">
<div class="pp-cover">
{% if project.img %}<img src="{{ project.img | prepend: '/' | relative_url }}" alt="{{ project.title }}" loading="lazy">{% else %}<div class="pp-placeholder"><i class="fa-solid fa-laptop-code"></i></div>{% endif %}
</div>
<div class="pp-body">
{% if project.period %}<div class="pp-period">{{ project.period }}</div>{% endif %}
<h3 class="pp-title"><a class="pp-link" href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
<p class="pp-desc">{{ project.description }}</p>
{% if project.github %}<div class="pp-actions"><a class="pp-btn" href="{{ project.github }}" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> GitHub</a></div>{% endif %}
</div>
</div>
{% endfor %}
</div>
<!-- prettier-ignore-end -->
