---
layout: page
permalink: /publications/
title: Publications
description: Explore my research journey in autonomous robotics through several publications. Covering diverse topics from uncertain multi-robot motion planning to explainable multi-agent path finding, each publication reflects a commitment to advancing algorithmic motion planning and task execution. Whether you're an academic colleague or a fellow researcher, I invite you to dive into the insights and solutions offered in this collection.
years: [2023, 2022, 2021]
nav: true
nav_order: 3
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
