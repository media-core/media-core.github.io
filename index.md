---
layout: default
title: Beranda
---

<style>
/* MEDIA CORE: BERANDA */
.mc-home { min-width: 0; }
.mc-home *, .mc-home *::before, .mc-home *::after { box-sizing: border-box; }
.mc-highlight { margin: 0 0 32px; overflow: hidden; border: 1px solid #d9e8fc; border-radius: 9px; background: #fff; box-shadow: 0 3px 12px rgba(0,65,160,.12); }
.mc-highlight-heading { display: flex; align-items: center; gap: 12px; margin: 0; padding: 13px 18px; color: #fff; background: linear-gradient(110deg,#071e59 0%,#0755b8 48%,#168cf0 100%); font-size: 20px; font-weight: 800; letter-spacing: .4px; }
.mc-highlight-icon { display: inline-grid; grid-template-columns: repeat(2,8px); gap: 3px; flex: none; }
.mc-highlight-icon span { display: block; width: 8px; height: 8px; background: #fff; opacity: .95; }
.mc-highlight-track { overflow: hidden; padding: 13px 0; }
.mc-highlight-marquee { display: flex; width: max-content; animation: mc-marquee 40s linear infinite; }
.mc-highlight-group { display: flex; flex: none; align-items: center; }
.mc-highlight-item { display: inline-flex; align-items: center; gap: 10px; padding: 0 22px; color: #17395f; font-size: 14px; font-weight: 700; text-decoration: none; white-space: nowrap; }
.mc-highlight-item:hover { color: #0878db; text-decoration: underline; }
.mc-highlight-item img { width: 52px; height: 36px; flex: none; object-fit: cover; border-radius: 4px; }
.mc-highlight-separator { color: #168cf0; font-size: 20px; }
.mc-highlight:hover .mc-highlight-marquee, .mc-highlight:focus-within .mc-highlight-marquee { animation-play-state: paused; }
@keyframes mc-marquee { from { transform: translateX(0); } to { transform: translateX(-50%); } }
.mc-intro { margin-bottom: 32px; }
.mc-intro h1 { font-size: 32px; line-height: 1.4; }
.mc-intro p { font-size: 16px; line-height: 1.8; }
.mc-content { display: grid; grid-template-columns: minmax(0,1fr) 235px; gap: 24px; align-items: start; }
.mc-latest, .mc-sidebar { min-width: 0; }
.mc-latest > h2 { margin: 0 0 20px; }
.mc-article-grid { display: grid; grid-template-columns: repeat(2,minmax(0,1fr)); gap: 18px; }
.mc-card { min-width: 0; overflow: hidden; border: 1px solid #e5e5e5; border-radius: 10px; background: #fff; }
.mc-card-image { display: block; }
.mc-card-image img { display: block; width: 100%; height: auto; aspect-ratio: 16/9; object-fit: cover; }
.mc-card-body { padding: 15px; }
.mc-card time { color: #777; font-size: 12px; }
.mc-card h3 { margin: 10px 0; font-size: 17px; line-height: 1.4; overflow-wrap: anywhere; }
.mc-card h3 a { color: #222; text-decoration: none; }
.mc-card h3 a:hover { color: #1756a9; }
.mc-card-description { color: #555; font-size: 14px; line-height: 1.65; overflow-wrap: anywhere; }
.mc-read-more { display: inline-block; margin-top: 8px; color: #1756a9; font-size: 14px; font-weight: 600; text-decoration: none; }
.mc-read-more:hover { text-decoration: underline; }
.mc-widget { margin-bottom: 20px; padding: 17px; border: 1px solid #e5e5e5; border-radius: 10px; background: #fff; }
.mc-widget h2 { margin: 0 0 12px; padding-bottom: 10px; border-bottom: 2px solid #1756a9; font-size: 18px; }
.mc-sidebar-list { list-style: none; padding: 0; margin: 0; }
.mc-sidebar-list li { padding: 10px 0; border-bottom: 1px solid #eee; font-size: 14px; line-height: 1.5; }
.mc-sidebar-list li:last-child { border-bottom: 0; }
.mc-sidebar-list a { color: #26394e; text-decoration: none; overflow-wrap: anywhere; }
.mc-sidebar-list a:hover { color: #1756a9; text-decoration: underline; }
.mc-count { color: #777; font-size: 12px; }
.mc-button { display: inline-block; padding: 11px 20px; border-radius: 7px; background: #1756a9; color: #fff !important; font-size: 14px; font-weight: 700; text-align: center; text-decoration: none; }
.mc-button:hover { background: #0b3977; }
.mc-widget .mc-button { display: block; margin-top: 14px; }
.mc-all-link { margin: 30px 0; text-align: center; }
@media (max-width: 760px) { .mc-content { grid-template-columns: minmax(0,1fr); } }
@media (max-width: 600px) { .mc-intro h1 { font-size: 26px; } .mc-article-grid { grid-template-columns: 1fr; } .mc-highlight-heading { font-size: 17px; } .mc-highlight-item { font-size: 13px; } }
@media (prefers-reduced-motion: reduce) { .mc-highlight-marquee { animation: none; width: auto; } .mc-highlight-group { flex-wrap: wrap; } .mc-highlight-group[aria-hidden="true"] { display: none; } .mc-highlight-item { white-space: normal; padding: 7px 16px; } }
</style>

{% assign mc_banners = site.static_files | where_exp: "file", "file.path contains '/assets/images/banner-'" %}
{% assign mc_banner_count = mc_banners.size %}
{% assign mc_posts = site.posts | sort: "date" | reverse %}

<div class="mc-home">
  <!-- HIGHLIGHT: 5 ARTIKEL TERBARU -->
  {% if mc_posts.size > 0 %}
  <section class="mc-highlight" aria-label="Highlight berita terbaru">
    <h2 class="mc-highlight-heading">
      <span class="mc-highlight-icon" aria-hidden="true"><span></span><span></span><span></span><span></span></span>
      HIGHLIGHT
    </h2>
    <div class="mc-highlight-track">
      <div class="mc-highlight-marquee">
        {% for copy in (1..2) %}
        <div class="mc-highlight-group" {% if copy == 2 %}aria-hidden="true"{% endif %}>
          {% for post in mc_posts limit:5 %}
            {% assign highlight_image = post.image %}
            {% unless highlight_image %}
              {% if mc_banner_count > 0 %}
                {% assign highlight_index = post.slug.size | modulo: mc_banner_count %}
                {% assign highlight_image = mc_banners[highlight_index].path %}
              {% endif %}
            {% endunless %}
            <a class="mc-highlight-item" href="{{ post.url | relative_url }}" {% if copy == 2 %}tabindex="-1"{% endif %}>
              {% if highlight_image %}<img src="{{ highlight_image | relative_url }}" alt="" width="52" height="36" loading="lazy">{% endif %}
              <span>{{ post.title | escape }}</span>
              <span class="mc-highlight-separator" aria-hidden="true">•</span>
            </a>
          {% endfor %}
        </div>
        {% endfor %}
      </div>
    </div>
  </section>
  {% endif %}

  <section class="mc-intro">
    <h1>Selamat Datang di Media Core</h1>
    <p>Media Core adalah portal informasi yang menyajikan berita dan artikel terbaru.</p>
    <p>Temukan berbagai informasi menarik seputar teknologi, bisnis, ekonomi, dan perkembangan dunia digital.</p>
  </section>

  <div class="mc-content">
    <section class="mc-latest" aria-label="Artikel terbaru">
      <h2>Artikel Terbaru</h2>
      <div class="mc-article-grid">
        {% for post in mc_posts limit:10 %}
          {% assign selected_image = post.image %}
          {% unless selected_image %}
            {% if mc_banner_count > 0 %}
              {% assign banner_index = post.slug.size | modulo: mc_banner_count %}
              {% assign selected_image = mc_banners[banner_index].path %}
            {% endif %}
          {% endunless %}
          <article class="mc-card">
            {% if selected_image %}
              <a class="mc-card-image" href="{{ post.url | relative_url }}">
                <img src="{{ selected_image | relative_url }}" alt="{{ post.title | escape }}" width="1280" height="720" loading="lazy" decoding="async">
              </a>
            {% endif %}
            <div class="mc-card-body">
              <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d-%m-%Y" }}</time>
              <h3><a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></h3>
              <p class="mc-card-description">{% if post.description %}{{ post.description | escape }}{% else %}{{ post.excerpt | strip_html | truncatewords: 25 }}{% endif %}</p>
              <a class="mc-read-more" href="{{ post.url | relative_url }}">Baca Selengkapnya →</a>
            </div>
          </article>
        {% endfor %}
      </div>
      <div class="mc-all-link"><a class="mc-button" href="{{ '/artikel/' | relative_url }}">Lihat Semua Artikel →</a></div>
    </section>

    <aside class="mc-sidebar" aria-label="Arsip dan artikel pilihan">
      <section class="mc-widget">
        <h2>Arsip Artikel</h2>
        <ul class="mc-sidebar-list">
          {% assign previous_month = '' %}
          {% for post in mc_posts %}
            {% assign current_month = post.date | date: '%Y-%m' %}
            {% if current_month != previous_month %}
              {% assign month_count = 0 %}
              {% for item in mc_posts %}
                {% assign item_month = item.date | date: '%Y-%m' %}
                {% if item_month == current_month %}{% assign month_count = month_count | plus: 1 %}{% endif %}
              {% endfor %}
              {% assign month_number = post.date | date: '%-m' %}
              {% assign month_names = 'Januari,Februari,Maret,April,Mei,Juni,Juli,Agustus,September,Oktober,November,Desember' | split: ',' %}
              {% assign month_index = month_number | minus: 1 %}
              <li><a href="{{ '/artikel/' | relative_url }}#bulan-{{ current_month }}">{{ month_names[month_index] }} {{ post.date | date: '%Y' }} <span class="mc-count">({{ month_count }} artikel)</span></a></li>
              {% assign previous_month = current_month %}
            {% endif %}
          {% endfor %}
        </ul>
        <a class="mc-button" href="{{ '/artikel/' | relative_url }}">Lihat Semua Arsip →</a>
      </section>
      <section class="mc-widget">
        <h2>Artikel Pilihan</h2>
        <ul class="mc-sidebar-list">
          {% for post in mc_posts limit:5 %}
            <li><a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></li>
          {% endfor %}
        </ul>
      </section>
    </aside>
  </div>
</div>
