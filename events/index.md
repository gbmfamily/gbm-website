---
layout: page
title: Events
---

# Upcoming Events

<ul>
{% for event in site.events %}
  <li>
    <a href="{{ event.url }}">{{ event.title }}</a> – {{ event.date | date: "%B %-d, %Y" }}
  </li>
{% endfor %}
</ul>