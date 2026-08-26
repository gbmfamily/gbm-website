---
layout: page
title: Our Fellowships
eyebrow: Find Your Community
subtitle: Every person has a place in the GBM family. Our fellowships are designed to help you grow in faith with people who understand your season of life.
permalink: /fellowships/
---

<section class="section">
  <div class="container">

    <!-- Colour coding for fellowship cards — cycles through brand colours -->
    {% assign colours = "var(--passion-red),var(--depth-blue),var(--harvest-green),var(--dark-blue),var(--passion-red),var(--harvest-green),var(--depth-blue),var(--passion-red)" | split: "," %}

    <div class="fellowships-grid reveal">
      {% for fellowship in site.fellowships %}
      {% assign colour = colours[forloop.index0 | modulo: colours.size] %}
      <div class="fellowship-card">
        {% if fellowship.banner %}
        <div class="fellowship-card-banner">
          <img src="{{ fellowship.banner | relative_url }}" alt="{{ fellowship.name }}" loading="lazy" />
        </div>
        {% else %}
        <div class="fellowship-card-color" style="background:{{ colour }};height:6px;"></div>
        {% endif %}
        <div class="fellowship-card-body">
          <h3>{{ fellowship.name }}</h3>
          <p>{{ fellowship.tagline }}</p>
          <div class="fellowship-card-meta">
            {% if fellowship.schedule %}<span>📅 {{ fellowship.schedule }}</span>{% endif %}
            {% if fellowship.time %}<span>🕐 {{ fellowship.time }}</span>{% endif %}
          </div>
          <a href="{{ fellowship.url | relative_url }}" class="btn btn-primary">Learn More</a>
        </div>
      </div>
      {% endfor %}
    </div>

  </div>
</section>

<!-- CTA strip -->
<section style="background:var(--dark-blue);padding:64px 0;text-align:center;">
  <div class="container">
    <span class="eyebrow" style="color:var(--passion-red);">You Belong Here</span>
    <h2 style="color:white;">There is a place for you</h2>
    <p style="color:rgba(255,255,255,0.65);max-width:480px;margin:12px auto 32px;">Whether you're a teenager, a student, a married couple, or a widow — Grace Bible Mission has a fellowship built for your season. Come as you are.</p>
    <a href="/assemblies/" class="btn btn-primary">Find an Assembly Near You</a>
  </div>
</section>
