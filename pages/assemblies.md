---
layout: page
title: Our Assemblies
eyebrow: Find Us Near You
subtitle: Grace Bible Mission has assemblies across Osogbo, Osun State and beyond. Find the one closest to you.
permalink: /assemblies/
---

<section class="section">
  <div class="container">

    <!-- Assembly grid — auto-populated from _assemblies/ folder -->
    <!-- HQ first, then all others -->
    {% assign hq = site.assemblies | where: "headquarters", true %}
    {% assign others = site.assemblies | where_exp: "a", "a.headquarters != true" %}
    {% assign ordered = hq | concat: others %}

    <div class="assemblies-grid reveal">
      {% for assembly in ordered %}
      <div class="assembly-listing-card {% if assembly.headquarters %}hq-card{% endif %}">
        {% if assembly.headquarters %}
        <div class="hq-card-banner">
          <span class="hq-badge">Headquarters</span>
        </div>
        {% endif %}
        <h3>{{ assembly.name }}</h3>
        <div class="detail-row">
          <span class="icon">📍</span>
          <span>{{ assembly.address }}</span>
        </div>
        <div class="detail-row">
          <span class="icon">🕐</span>
          <div>
            {% for time in assembly.service_times %}
            <div>{{ time }}</div>
            {% endfor %}
          </div>
        </div>
        {% if assembly.pastor and assembly.pastor.name != "To Be Updated" %}
        <div class="detail-row">
          <span class="icon">👤</span>
          <span>{{ assembly.pastor.name }}</span>
        </div>
        {% endif %}
        <a href="{{ assembly.url | relative_url }}" class="btn btn-primary">View Assembly</a>
      </div>
      {% endfor %}
    </div>

  </div>
</section>

<!-- CTA -->
<section style="background:var(--off-white);padding:64px 0;text-align:center;">
  <div class="container">
    <span class="eyebrow">New to GBM?</span>
    <h2>Not sure where to start?</h2>
    <p style="color:var(--text-light);max-width:440px;margin:12px auto 32px;">Visit any of our assemblies — you'll find a warm welcome, the Word of God, and a community that will feel like home.</p>
    <a href="/about/" class="btn btn-primary">Learn More About Us</a>
  </div>
</section>
