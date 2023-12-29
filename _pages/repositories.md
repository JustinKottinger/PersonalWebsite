---
layout: page
permalink: /repositories/
title: Repositories
description: Discover the code behind my research and projects on the Repositories page. This collection showcases GitHub repositories where I've created and contributed code, providing a hands-on view of my work in autonomous motion and task planning. Whether you're a developer, collaborator, or simply curious about the technical side of my projects, explore these repositories to gain direct access to the code that powers advancements in autonomous robotics.
nav: true
nav_order: 4
---

## GitHub Account

{% if site.data.repositories.github_users %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.html username=user %}
  {% endfor %}
</div>
{% endif %}

---

## GitHub Repositories

{% if site.data.repositories.github_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}
</div>
{% endif %}
