---
layout: default
title: Courses
permalink: /courses/
---

# Courses

<ul>
{% for course in site.courses %}
  {% unless course.module %}
  <li>
    <a href="{{ course.url | relative_url }}">{{ course.title }}</a>
    {% if course.status %}<em>({{ course.status }})</em>{% endif %}
    <br>{{ course.summary }}
  </li>
  {% endunless %}
{% endfor %}
</ul>
