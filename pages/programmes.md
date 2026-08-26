---
layout: page
title: Programmes
eyebrow: Special Events
subtitle: Grace Bible Mission hosts special programmes throughout the year — encounters with God through the Word, worship, and fellowship.
permalink: /programmes/
---

<section class="section">
  <div class="container">

    <div class="programmes-listing-grid reveal">
      {% for programme in site.programmes %}
      <div class="programme-card">
        <div class="programme-card-banner">
          {% if programme.banner %}
          <img src="{{ programme.banner | relative_url }}" alt="{{ programme.title }}" loading="lazy" />
          {% else %}
          <div style="width:100%;height:100%;background:linear-gradient(135deg,var(--depth-blue),var(--dark-blue));"></div>
          {% endif %}
          <span class="card-type">Special Programme</span>
        </div>
        <div class="programme-card-body">
          <h3>{{ programme.title }}</h3>
          <div class="programme-meta">
            {% if programme.dates %}<span>📅 {{ programme.dates }}</span>{% endif %}
            {% if programme.time %}<span>🕐 {{ programme.time }}</span>{% endif %}
            {% if programme.venue %}<span>📍 {{ programme.venue }}</span>{% endif %}
          </div>
          <p>{{ programme.content | strip_html | truncate: 160 }}</p>
          <a href="{{ programme.url | relative_url }}" class="btn btn-primary">Details</a>
        </div>
      </div>
      {% endfor %}
    </div>

    <!-- If no programmes exist yet -->
    {% if site.programmes.size == 0 %}
    <div class="text-center" style="padding:80px 0;">
      <h3 style="color:var(--text-muted);">No programmes listed yet</h3>
      <p style="color:var(--text-muted);">Check back soon or follow our announcements for upcoming events.</p>
    </div>
    {% endif %}

  </div>
</section>
