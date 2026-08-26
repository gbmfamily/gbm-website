---
layout: home
title: Home
---

<!-- ══════════════════════════════════════════════════════════
     HERO
     ══════════════════════════════════════════════════════════ -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="container">
    <div class="hero-content">
      <div class="hero-eyebrow">
        <span>Grace Bible Mission</span>
      </div>
      <h1>
        Bringing Many
        <span class="highlight">Sons to Glory</span>
      </h1>
      <p class="hero-sub">
        A dynamic church proclaiming the Word of God — making disciples for our Lord Jesus Christ by Exalting God, Encouraging believers, Equipping Christians, and Evangelizing the World.
      </p>
      <div class="hero-actions">
        <a href="/assemblies/" class="btn btn-primary">Find an Assembly</a>
        <a href="/about/" class="btn btn-outline">About GBM</a>
      </div>
    </div>
  </div>
</section>

<!-- Motto strip -->
<div class="motto-strip">
  <p>Preach <span>·</span> Teach <span>·</span> Disciple</p>
</div>


<!-- ══════════════════════════════════════════════════════════
     WHAT WE BELIEVE (3-pillar strip)
     ══════════════════════════════════════════════════════════ -->
<section class="section">
  <div class="about-strip reveal">
    <div class="about-pillar pillar-color-1">
      <div class="pillar-number">01</div>
      <span class="pillar-accent"></span>
      <h3>Exalt God</h3>
      <p>We gather to worship God in spirit and in truth — every service, every song, every prayer is an act of surrender to the King of Kings.</p>
    </div>
    <div class="about-pillar pillar-color-2">
      <div class="pillar-number">02</div>
      <span class="pillar-accent"></span>
      <h3>Equip Believers</h3>
      <p>We are committed to building believers to maturity in Christ — through the Word, the Spirit, and meaningful community.</p>
    </div>
    <div class="about-pillar pillar-color-3">
      <div class="pillar-number">03</div>
      <span class="pillar-accent"></span>
      <h3>Evangelise the World</h3>
      <p>From Osogbo to the ends of the earth — we exist to plant Acts-of-the-Apostles churches and reach every soul with the gospel.</p>
    </div>
  </div>
</section>


<!-- ══════════════════════════════════════════════════════════
     SPECIAL PROGRAMMES
     ══════════════════════════════════════════════════════════ -->
<section class="section section-alt">
  <div class="container">
    <div class="section-header-row">
      <div>
        <span class="eyebrow">Special Events</span>
        <h2>Upcoming Programmes</h2>
      </div>
      <a href="/programmes/" class="btn btn-outline" style="background:transparent;color:var(--depth-blue);border-color:var(--depth-blue);">All Programmes →</a>
    </div>

    <div class="programmes-grid">
      {% assign featured = site.programmes | where: "featured", true | limit: 3 %}
      {% for programme in featured %}
      <div class="programme-card reveal">
        <div class="programme-card-banner">
          {% if programme.banner %}
          <img src="{{ programme.banner | relative_url }}" alt="{{ programme.title }}" loading="lazy" />
          {% else %}
          <div style="width:100%;height:100%;background:var(--depth-blue);"></div>
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
          <p>{{ programme.content | strip_html | truncate: 120 }}</p>
          <a href="{{ programme.url | relative_url }}" class="btn btn-primary">Learn More</a>
        </div>
      </div>
      {% endfor %}
    </div>
  </div>
</section>


<!-- ══════════════════════════════════════════════════════════
     WEEKLY SCHEDULE
     ══════════════════════════════════════════════════════════ -->
<section class="section section-dark">
  <div class="container">
    <div class="section-header">
      <span class="eyebrow" style="color:var(--passion-red);">Every Week</span>
      <h2>Our Regular Programmes</h2>
      <p>Join us every week for worship, the Word, and fellowship. All are welcome.</p>
    </div>

    <div class="schedule-grid reveal">
      {% for day in site.data.weekly_schedule %}
      <div class="schedule-day">
        <h4>{{ day.day }}</h4>
        {% for prog in day.programmes %}
        <div class="schedule-item">
          <span class="prog-name">{{ prog.name }}</span>
          <span class="time">{{ prog.time }}</span>
        </div>
        {% endfor %}
      </div>
      {% endfor %}
    </div>
  </div>
</section>


<!-- ══════════════════════════════════════════════════════════
     ASSEMBLIES PREVIEW
     ══════════════════════════════════════════════════════════ -->
<section class="section">
  <div class="container">
    <div class="section-header-row">
      <div>
        <span class="eyebrow">Find Us Near You</span>
        <h2>Our Assemblies</h2>
      </div>
      <a href="/assemblies/" class="btn btn-primary">All Assemblies →</a>
    </div>

    {% assign hq = site.assemblies | where: "headquarters", true %}
    {% assign others = site.assemblies | where_exp: "a", "a.headquarters != true" %}
    {% assign ordered = hq | concat: others %}

    <div class="assemblies-preview reveal">
      {% for assembly in ordered limit: 6 %}
      <a href="{{ assembly.url | relative_url }}" class="assembly-card {% if assembly.headquarters %}assembly-card-hq{% endif %}">
        {% if assembly.headquarters %}<span class="hq-badge" style="margin-bottom:8px;">Headquarters</span>{% endif %}
        <div class="assembly-card-name">{{ assembly.name }}</div>
        <div class="assembly-card-addr">📍 {{ assembly.address }}</div>
        <div class="assembly-card-times">
          {% for time in assembly.service_times limit: 1 %}{{ time }}{% endfor %}
        </div>
        <div class="assembly-card-arrow">More Info →</div>
      </a>
      {% endfor %}
    </div>
  </div>
</section>


<!-- ══════════════════════════════════════════════════════════
     CONNECT / CTA
     ══════════════════════════════════════════════════════════ -->
<section class="connect-section">
  <div class="container">
    <span class="eyebrow" style="color:rgba(255,255,255,0.5);">Stay Connected</span>
    <h2>Join the GBM Family</h2>
    <p>Stay updated with our latest messages, events and announcements. Connect with us on YouTube for sermons and programmes.</p>
    <div class="connect-actions">
      <a href="{{ site.church.youtube }}" class="btn btn-primary" target="_blank" rel="noopener">Watch on YouTube</a>
      <a href="/fellowships/" class="btn btn-outline">Find a Fellowship</a>
    </div>
  </div>
</section>
