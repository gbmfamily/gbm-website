---
layout: page
title: Pastors
---

# Our Pastors

<ul>
{% for pastor in site.pastors %}
  <li>
    <a href="{{ pastor.url }}">{{ pastor.name }}</a> – {{ pastor.assembly }}
  </li>
{% endfor %}
</ul>