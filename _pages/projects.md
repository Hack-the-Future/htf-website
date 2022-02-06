---
title: "Projects"
permalink: /projects//
layout: single
---

{% for project in site.data.projects %}
{% include project.html project = project %}
{% endfor %}
