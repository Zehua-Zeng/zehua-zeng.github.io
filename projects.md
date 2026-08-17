---
layout: page
permalink: /projects/
title: Projects
class: projects
---

{:.hidden}

# Projects

{:.lead}
A collection of research, coursework, and side projects. I’m currently sorting through some of my older projects and code, so more will be added soon. ;) Feel free to reach out for a demo if a project’s repository is not publicly available.

<div class="grid">
  {% for project in site.data.projects %}
    {% include project.html project=project %}
  {% endfor %}
</div>
