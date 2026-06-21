---
layout: default
title: Kapcsolat
permalink: /kapcsolat/
---

<section class="hero">
  <div class="wrap">
    <p class="eyebrow">Elérhetőség</p>
    <h1>Kapcsolat</h1>
    <p class="sub">Kognitív Tudományi Tanszék, BME Természettudományi Kar.</p>
  </div>
</section>

<section class="section">
  <div class="wrap">
    <div class="contact-grid">
      <div class="prose">
        <dl class="facts" style="grid-template-columns:1fr">
          <div class="fact"><dt>Cím</dt><dd>{{ site.contact.address }}</dd></div>
          <div class="fact"><dt>Telefon</dt><dd><a href="tel:+3614631273">{{ site.contact.phone }}</a></dd></div>
          <div class="fact"><dt>E-mail</dt><dd><a href="mailto:{{ site.contact.email }}">{{ site.contact.email }}</a></dd></div>
          <div class="fact"><dt>Facebook</dt><dd><a href="{{ site.contact.facebook }}">facebook.com/BME.KOGNITIV</a></dd></div>
        </dl>
      </div>
      <!-- Map: simple Google Maps embed by address, no API key needed.
           Replace the q= value if a more precise pin is wanted. -->
      <iframe
        title="Térkép"
        loading="lazy"
        src="https://www.google.com/maps?q=BME+T+épület+Egry+József+utca+1+Budapest&output=embed"></iframe>
    </div>
  </div>
</section>
