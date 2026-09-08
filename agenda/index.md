---
layout: default
title: Agenda
permalink: /agenda/
---

# Agenda

{% assign today = "now" | date: "%s" %}
{% assign upcoming = "" | split: "" %}
{% assign past = "" | split: "" %}

{% for event in site.events %}
  {% assign event_ts = event.date | date: "%s" %}
  {% if event_ts >= today %}
    {% assign upcoming = upcoming | push: event %}
  {% else %}
    {% assign past = past | push: event %}
  {% endif %}
{% endfor %}

{% assign upcoming = upcoming | sort: "date" %}
{% assign past = past | sort: "date" | reverse %}

## Upcoming

<ul>
{% for event in upcoming %}
  <li>
    <strong>{{ event.date | date: "%-d %B %Y" }}</strong>
    {% if event.end_date %}– {{ event.end_date | date: "%-d %B %Y" }}{% endif %}
    — {{ event.title }}
    {% if event.location %}({{ event.location }}){% endif %}
    {% if event.registration_url %}
      — <a href="{{ event.registration_url }}">register</a>
    {% endif %}
  </li>
{% else %}
  <li>No upcoming sessions scheduled yet.</li>
{% endfor %}
</ul>

## Past

<ul>
{% for event in past %}
  <li>{{ event.date | date: "%-d %B %Y" }} — {{ event.title }}</li>
{% endfor %}
</ul>