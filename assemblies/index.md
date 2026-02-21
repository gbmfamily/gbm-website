---
layout: page
title: Assemblies
---

# Our Assemblies

<ul>
{% for assembly in site.assemblies %}
  <li>
    <a href="{{ assembly.url }}">{{ assembly.title }}</a> – {{ assembly.location }}
  </li>
{% endfor %}
</ul>