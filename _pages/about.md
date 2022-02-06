---
title: "About"
permalink: /about/
layout: single
noindex: true
---

## Mission

We at HTF hope to make a positive impact in the community through software
design and development. We aim to be actively involved with nonprofits in the
nearby area by helping to build and maintain software solutions at no cost. We
also want to foster an environment among our team that brings together fun,
learning, and social aspects.

## Board

{% assign year = "now" | date: "%Y" | plus: 0 %}

<!-- Include current members only !-->
{% for person in site.data.people %}
{% assign period = person.roles | where: "year", year | first %}
{% if period %}
{% include person.html person = person %}
{% endif %}
{% endfor %}
