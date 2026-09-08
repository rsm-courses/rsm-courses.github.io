---
layout: default
title: Home
---

# RSM Courses

Welcome! This site collects the courses and self-guided teaching materials
offered by the Research Software Management team.

## Current courses

<ul>
{% for course in site.courses %}
  <li>
    <a href="{{ course.url | relative_url }}">{{ course.title }}</a>
    {% if course.status %}<em>({{ course.status }})</em>{% endif %}
    — {{ course.summary }}
  </li>
{% endfor %}
</ul>

See the [Courses](/courses/) page for the full list, or [Materials](/materials/)
for self-guided lessons you can work through on your own.