---
layout: page
title: About GBM
eyebrow: Who We Are
subtitle: Grace Bible Mission — a church rooted in the Word, Spirit-filled, and sent into the world.
permalink: /about/
---

<!-- Vision & Mission -->
<section class="section">
  <div class="about-vision-mission reveal">
    <div class="vm-card vm-vision">
      <h3>Our Vision</h3>
      <blockquote>Bringing Many Sons to Glory</blockquote>
      <cite>Hebrews 2:10</cite>
    </div>
    <div class="vm-card vm-mission">
      <h3>Our Mission</h3>
      <blockquote>Make disciples for our Lord Jesus Christ</blockquote>
      <cite>By Exalting God · Encouraging Believers · Equipping Christians · Evangelizing the World</cite>
    </div>
  </div>
</section>

<!-- Motto -->
<section style="background:var(--passion-red);padding:32px 0;text-align:center;">
  <div class="container">
    <span class="eyebrow" style="color:rgba(255,255,255,0.6);">Our Motto</span>
    <h2 style="color:white;font-size:2.5rem;letter-spacing:0.2em;">PREACH · TEACH · DISCIPLE</h2>
    <p style="color:rgba(255,255,255,0.75);margin-top:8px;margin-bottom:0;">Colossians 1:28 · II Timothy 2:2</p>
  </div>
</section>

<!-- Core Beliefs -->
<section class="section">
  <div class="container">
    <div class="section-header reveal">
      <span class="eyebrow">What We Believe</span>
      <h2>Core Beliefs</h2>
    </div>
    <div class="beliefs-grid reveal">
      <div class="belief-card">
        <h3>Grace & Salvation</h3>
        <p>We believe that the grace of God leads every soul to salvation — freely given, undeserved, and transforming.</p>
      </div>
      <div class="belief-card">
        <h3>Sanctification</h3>
        <p>We believe that God's grace does not stop at salvation but continues to sanctify the believer, setting them apart for His purposes.</p>
      </div>
      <div class="belief-card">
        <h3>Service</h3>
        <p>We believe that grace compels us to serve — in the church, in the community, and in every sphere of life.</p>
      </div>
    </div>
  </div>
</section>

<!-- Statement of Purpose -->
<section class="section section-alt">
  <div class="container">
    <div class="section-header reveal">
      <span class="eyebrow">Our Calling</span>
      <h2>Statement of Purpose</h2>
    </div>
    <div class="purpose-list reveal">
      <div class="purpose-item"><p>To lead men to be genuinely born again — saved from sin, bondage to idolatry, false religion, selfishness, corruption and all that debarment from heaven, through the knowledge of our Lord Jesus Christ.</p></div>
      <div class="purpose-item"><p>To build men up to grow to maturity spiritually and become Christlike at home, at work, in society and in the house of God through the fullness and indwelling power of the Holy Spirit.</p></div>
      <div class="purpose-item"><p>To lead men to walk in dominion over every demonic influence and power through the supernatural power of God, so as to enjoy the full benefits of the gospel.</p></div>
      <div class="purpose-item"><p>To train and equip men to fulfil the Great Commission — evangelising the world for Christ and receiving eternal reward.</p></div>
      <div class="purpose-item"><p>To plant Acts-of-the-Apostles churches — Grace Bible Churches — through the whole world before our Lord returns, beginning from Osogbo and widening therefrom in ripples through Osun State, Nigeria, Africa and the World.</p></div>
      <div class="purpose-item"><p>To prepare men without spot or wrinkle for the glorious appearing of our Lord from heaven, that they may enjoy the Kingdom of God forever.</p></div>
      <div class="purpose-item"><p>To glorify God in worship, in ministry and in all we do.</p></div>
    </div>
  </div>
</section>

<!-- Weekly Schedule -->
<section class="section section-dark">
  <div class="container">
    <div class="section-header reveal">
      <span class="eyebrow" style="color:var(--passion-red);">Join Us</span>
      <h2>Weekly Programmes</h2>
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

<!-- Leadership -->
<section class="section">
  <div class="container">
    <div class="section-header reveal">
      <span class="eyebrow">Servant Leaders</span>
      <h2>National Leadership</h2>
    </div>
    <!-- General Overseer — featured card (first entry in _data/leadership.yml) -->
    {% assign go = site.data.leadership[0] %}
    <div class="leader-featured-card reveal">
      <div class="leader-featured-photo">
        {% if go.photo and go.photo != "" %}
        <img src="{{ go.photo | relative_url }}" alt="{{ go.name }}" loading="lazy" />
        {% else %}
        <div class="leader-initials" style="height:100%;">{{ go.name | slice: 0 }}</div>
        {% endif %}
      </div>
      <div class="leader-featured-body">
        <span class="leader-title">{{ go.title }}</span>
        <h3>{{ go.name }}</h3>
        {% if go.bio %}<p>{{ go.bio }}</p>{% endif %}
      </div>
    </div>

    <!-- Remaining leadership -->
    <div class="leadership-grid reveal" style="margin-top:32px;">
      {% for leader in site.data.leadership offset:1 %}
      <div class="leader-card">
        <div class="leader-photo-wrapper">
          {% if leader.photo and leader.photo != "" %}
          <img src="{{ leader.photo | relative_url }}" alt="{{ leader.name }}" loading="lazy" />
          {% else %}
          <div class="leader-initials">{{ leader.name | slice: 0 }}</div>
          {% endif %}
        </div>
        <div class="leader-card-body">
          <span class="leader-title">{{ leader.title }}</span>
          <h4>{{ leader.name }}</h4>
        </div>
      </div>
      {% endfor %}
    </div>
  </div>
</section>

<!-- History -->
<section class="section section-alt">
  <div class="container">
    <div class="section-header reveal">
      <span class="eyebrow">Since 1987</span>
      <h2>Our History</h2>
    </div>
    <div class="history-section reveal">
      <p>The history of Grace Bible Mission cannot be complete without reference to Ebenezer Baptist Church, Osogbo — from which the majority of the pioneering members emerged.</p>

      <p>Grace Bible Mission, formerly known as Grace Baptist Church, with her headquarters at No. 1, Grace Bible Mission Street, Oke-Oniti, Osogbo, was inaugurated on <strong>April 12, 1987</strong>. The birth of the church was not pre-planned but borne out of a leadership crisis between Ebenezer Baptist Church and Union Baptist Church, Osogbo (the mother church). What began in persecution and division became, by the grace of God, a thriving church committed to the Word.</p>

      <p>On April 12, 1987 — during a church business meeting — the majority of the church officers tendered letters of resignation and resolved that it was better to separate in peace. Grace Baptist Church (Fundamental, Independent), Osogbo was born that very evening, with 254 people in attendance at the inaugural worship service. Brother Julius O. Ogunlokola, now the General Overseer, officiated.</p>

      <p>Two acres of land were acquired for the permanent site on January 21, 1990. The foundation of the 2,500-capacity headquarters auditorium was laid on Saturday, June 24, 1989 — completed in nine months, beginning with only two thousand naira in the church's account. To the glory of God, she was not put to shame.</p>

      <p>On August 27, 1992, the Federal Ministry of Internal Affairs granted final approval for the church's registration. Today, Grace Bible Mission stands as a testament to what God can do when a people resolves to stand for His Word — growing from 254 founding members to a family of assemblies, fellowships, and disciples reaching across Nigeria and beyond.</p>
    </div>
  </div>
</section>

<!-- Contact anchor -->
<section class="section" id="contact">
  <div class="container">
    <div class="text-center" style="margin-bottom:40px;">
      <span class="eyebrow">Get in Touch</span>
      <h2>Visit Us</h2>
      <p style="color:var(--text-light);max-width:480px;margin:12px auto 16px;">Our doors are always open. Find an assembly near you or reach us at our headquarters in Osogbo.</p>
      <p style="color:var(--text-light);margin-bottom:8px;">📍 {{ site.church.address }}</p>
      {% if site.church.email %}<p><a href="mailto:{{ site.church.email }}">{{ site.church.email }}</a></p>{% endif %}
      <div style="margin-top:24px;">
        <a href="/assemblies/" class="btn btn-primary">Find an Assembly Near You</a>
      </div>
    </div>
    <div class="map-container" style="border-radius:var(--radius-lg);overflow:hidden;border:1px solid var(--light-gray);">
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3952.9609019546538!2d4.557968973578253!3d7.793964507100201!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x103787d78372bea3%3A0xe170bca9cbbc5d55!2sGrace%20Bible%20Mission%20Headquarters!5e0!3m2!1sen!2sza!4v1787755401546!5m2!1sen!2sza" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="strict-origin-when-cross-origin"></iframe>
    </div>
  </div>
</section>
