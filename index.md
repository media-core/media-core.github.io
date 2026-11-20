---
layout: default
title: Beranda
---

<style>
/* MEDIA CORE PREMIUM — hanya untuk beranda */
body:has(.mc-home) { background:#f2f6ff; }
body:has(.mc-home) .page-content > .wrapper { max-width:1320px; padding-left:22px; padding-right:22px; }
body:has(.mc-home) .page-content { padding-top:24px; }
.mc-home,.mc-home * { box-sizing:border-box; }
.mc-home { color:#10254b; font-family:system-ui,-apple-system,"Segoe UI",sans-serif; }
.mc-home a { text-decoration:none; }
.mc-hero { position:relative; isolation:isolate; overflow:hidden; min-height:365px; display:flex; align-items:center; padding:50px 5.5%; border-radius:23px; background:radial-gradient(circle at 83% 30%,#2451a8 0%,transparent 35%),linear-gradient(120deg,#061734 0%,#102a62 57%,#061734 100%); color:white; box-shadow:0 18px 38px rgba(8,34,83,.18); }
.mc-hero:before { content:""; position:absolute; z-index:-1; right:-80px; top:-180px; width:530px; height:530px; border:2px solid rgba(40,225,255,.25); border-radius:50%; box-shadow:0 0 0 48px rgba(44,121,255,.06),0 0 0 105px rgba(44,121,255,.045); }
.mc-hero:after { content:""; position:absolute; z-index:-1; right:10%; bottom:-170px; width:430px; height:360px; border-radius:50%; background:#00d9ff; filter:blur(110px); opacity:.13; }
.mc-hero-copy { max-width:750px; position:relative; z-index:1; }
.mc-eyebrow { margin:0 0 18px; color:#42e7ff; font-size:13px; letter-spacing:3px; font-weight:850; text-transform:uppercase; }
.mc-hero h1 { margin:0 0 20px; color:#fff; font-size:clamp(29px,4vw,53px); line-height:1.14; font-weight:850; letter-spacing:-1.4px; }
.mc-hero h1 span { color:#40e5ff; }
.mc-hero p.mc-subtitle { max-width:660px; margin:0 0 26px; color:#e0edff; font-size:16px; line-height:1.8; }
.mc-tags { display:flex; flex-wrap:wrap; gap:10px; }
.mc-tags span { border:1px solid rgba(82,218,255,.4); border-radius:100px; background:rgba(2,31,76,.55); padding:10px 15px; font-size:12px; font-weight:700; color:#e9faff; }
.mc-hero-art { position:absolute; right:3%; top:50%; transform:translateY(-50%); font-size:150px; line-height:1; opacity:.28; filter:drop-shadow(0 0 28px #21c9ff); pointer-events:none; }
.mc-section-head { display:flex; align-items:center; justify-content:space-between; gap:12px; margin:0 0 20px; }
.mc-section-head h2 { margin:0; font-size:25px; font-weight:850; color:#0b2454; letter-spacing:-.5px; }
.mc-section-head a { color:#0865c7; font-weight:750; font-size:13px; }
.mc-highlight { margin:28px 0 35px; overflow:hidden; border-radius:19px; background:white; box-shadow:0 10px 28px rgba(23,61,121,.09); border:1px solid #e3ebf9; }
.mc-highlight-top { display:flex; align-items:center; justify-content:space-between; padding:15px 22px; background:linear-gradient(110deg,#0b2355,#1451ae 65%,#1376d2); color:white; }
.mc-highlight-top h2 { margin:0; font-size:21px; font-weight:850; color:white; }
.mc-highlight-top small { color:#cbeaff; font-weight:650; }
.mc-feature { display:grid; grid-template-columns:190px minmax(0,1fr); gap:24px; align-items:center; padding:22px; }
.mc-feature-img { display:block; overflow:hidden; border-radius:13px; aspect-ratio:16/10; background:linear-gradient(135deg,#0b2355,#1889d5); }
.mc-feature-img img { width:100%; height:100%; object-fit:cover; display:block; }
.mc-feature h3 { margin:0 0 11px; font-size:clamp(18px,2vw,24px); line-height:1.35; font-weight:800; }
.mc-feature h3 a { color:#0b2454; }
.mc-feature h3 a:hover { color:#087ed8; }
.mc-feature p { margin:0 0 12px; color:#526580; line-height:1.65; font-size:14px; }
.mc-feature-meta { font-size:12px; color:#6481a8; font-weight:700; }
.mc-content { display:grid; grid-template-columns:minmax(0,1fr) 275px; gap:26px; align-items:start; }
.mc-article-grid { display:grid; grid-template-columns:repeat(2,minmax(0,1fr)); gap:20px; }
.mc-card { overflow:hidden; min-width:0; border-radius:17px; background:white; border:1px solid #e3ebf9; box-shadow:0 6px 20px rgba(23,61,121,.06); transition:transform .2s,box-shadow .2s; }
.mc-card:hover { transform:translateY(-4px); box-shadow:0 15px 30px rgba(23,61,121,.13); }
.mc-card-image { display:block; overflow:hidden; aspect-ratio:16/9; background:#102a62; }
.mc-card-image img { display:block; width:100%; height:100%; object-fit:cover; transition:transform .3s; }
.mc-card:hover .mc-card-image img { transform:scale(1.04); }
.mc-card-body { padding:20px; }
.mc-card time { color:#68809e; font-size:12px; font-weight:650; }
.mc-card h3 { margin:11px 0; font-size:18px; line-height:1.45; font-weight:800; overflow-wrap:anywhere; }
.mc-card h3 a { color:#11264c; }
.mc-card h3 a:hover { color:#087ed8; }
.mc-card-description { color:#61728a; font-size:13px; line-height:1.7; margin:0 0 13px; }
.mc-read-more { color:#0875d5; font-weight:800; font-size:13px; }
.mc-widget { background:white; border:1px solid #e3ebf9; border-radius:17px; padding:20px; margin-bottom:20px; box-shadow:0 6px 20px rgba(23,61,121,.06); }
.mc-widget h2 { margin:0 0 13px; padding-bottom:13px; border-bottom:2px solid #dbeaff; color:#102a62; font-size:18px; font-weight:850; }
.mc-sidebar-list { list-style:none; margin:0; padding:0; }
.mc-sidebar-list li { padding:11px 0; border-bottom:1px solid #edf2f9; line-height:1.5; font-size:13px; }
.mc-sidebar-list li:last-child { border-bottom:0; }
.mc-sidebar-list a { color:#273c5b; overflow-wrap:anywhere; }
.mc-sidebar-list a:hover { color:#0875d5; }
.mc-count { color:#7b8da5; font-size:12px; }
.mc-button { display:inline-block; border-radius:100px; padding:12px 22px; background:linear-gradient(105deg,#075bd5,#03bde5); color:white!important; font-size:13px; font-weight:800; text-align:center; box-shadow:0 6px 16px rgba(0,135,218,.2); }
.mc-widget .mc-button { display:block; margin-top:15px; }
.mc-all-link { text-align:center; margin:28px 0 42px; }
@media(max-width:900px) { .mc-content { grid-template-columns:1fr; } .mc-sidebar { display:grid; grid-template-columns:repeat(2,minmax(0,1fr)); gap:16px; } .mc-widget { margin-bottom:0; } }
@media(max-width:640px) { body:has(.mc-home) .page-content > .wrapper { padding-left:14px; padding-right:14px; } .mc-hero { min-height:340px; padding:34px 25px; border-radius:16px; } .mc-hero-art { font-size:110px; right:-20px; opacity:.13; } .mc-eyebrow { font-size:10px; letter-spacing:1.6px; } .mc-hero h1 { letter-spacing:-.5px; } .mc-hero p.mc-subtitle { font-size:14px; } .mc-tags span { font-size:11px; padding:8px 10px; } .mc-feature { grid-template-columns:1fr; gap:14px; padding:16px; } .mc-feature-img { aspect-ratio:16/9; } .mc-article-grid,.mc-sidebar { grid-template-columns:1fr; } .mc-section-head h2 { font-size:21px; } }
@media(prefers-reduced-motion:reduce) { .mc-card,.mc-card-image img { transition:none; } }
</style>

{% assign mc_posts = site.posts | sort: 'date' | reverse %}
{% assign mc_banners = site.static_files | where_exp: 'file', "file.path contains '/assets/images/banner-'" %}
{% assign mc_banner_count = mc_banners.size %}

<div class="mc-home">
  <section class="mc-hero" aria-label="Selamat datang di Media Core">
    <div class="mc-hero-copy">
      <p class="mc-eyebrow">Wawasan Digital · Budaya · Teknologi</p>
      <h1>Jendela Informasi untuk <span>Dunia yang Terus Bergerak</span></h1>
      <p class="mc-subtitle">Selamat datang di Media Core. Jelajahi artikel tentang teknologi, budaya, tren kreatif, dan hiburan digital dalam satu ruang baca.</p>
      <div class="mc-tags"><span>✦ Teknologi Digital</span><span>✦ Budaya &amp; Tren Kreatif</span><span>✦ Hiburan Digital</span></div>
    </div>
    <div class="mc-hero-art" aria-hidden="true">✦</div>
  </section>

  {% if mc_posts.size > 0 %}
  {% assign featured = mc_posts.first %}
  {% assign featured_image = featured.image %}
  {% unless featured_image %}{% if mc_banner_count > 0 %}{% assign fallback_index = featured.slug.size | modulo: mc_banner_count %}{% assign featured_image = mc_banners[fallback_index].path %}{% endif %}{% endunless %}
  <section class="mc-highlight" aria-label="Highlight artikel">
    <div class="mc-highlight-top"><h2>✦ HIGHLIGHT</h2><small>Topik Pilihan</small></div>
    <article class="mc-feature">
      {% if featured_image %}<a class="mc-feature-img" href="{{ featured.url | relative_url }}"><img src="{{ featured_image | relative_url }}" alt="{{ featured.title | escape }}" width="640" height="400" fetchpriority="high"></a>{% endif %}
      <div>
        <h3><a href="{{ featured.url | relative_url }}">{{ featured.title | escape }}</a></h3>
        <p>{% if featured.description %}{{ featured.description | escape }}{% else %}{{ featured.excerpt | strip_html | truncatewords: 26 }}{% endif %}</p>
        <div class="mc-feature-meta">{{ featured.date | date: '%d-%m-%Y' }} · MEDIA CORE</div>
        <p style="margin:14px 0 0"><a class="mc-button" href="{{ featured.url | relative_url }}">Baca Artikel →</a></p>
      </div>
    </article>
  </section>
  {% endif %}

  <div class="mc-content">
    <section class="mc-latest" aria-label="Artikel terbaru">
      <div class="mc-section-head"><h2>Artikel Terbaru</h2><a href="{{ '/artikel/' | relative_url }}">Lihat Semua →</a></div>
      <div class="mc-article-grid">
        {% for post in mc_posts limit:10 %}
          {% assign selected_image = post.image %}
          {% unless selected_image %}{% if mc_banner_count > 0 %}{% assign banner_index = post.slug.size | modulo: mc_banner_count %}{% assign selected_image = mc_banners[banner_index].path %}{% endif %}{% endunless %}
          <article class="mc-card">
            {% if selected_image %}<a class="mc-card-image" href="{{ post.url | relative_url }}"><img src="{{ selected_image | relative_url }}" alt="{{ post.title | escape }}" width="640" height="360" loading="lazy" decoding="async"></a>{% endif %}
            <div class="mc-card-body">
              <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%d-%m-%Y' }}</time>
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
          {% assign month_names = 'Januari,Februari,Maret,April,Mei,Juni,Juli,Agustus,September,Oktober,November,Desember' | split: ',' %}
          {% for post in mc_posts %}
            {% assign current_month = post.date | date: '%Y-%m' %}
            {% if current_month != previous_month %}
              {% assign month_count = 0 %}
              {% for item in mc_posts %}{% assign item_month = item.date | date: '%Y-%m' %}{% if item_month == current_month %}{% assign month_count = month_count | plus: 1 %}{% endif %}{% endfor %}
              {% assign month_index = post.date | date: '%-m' | minus: 1 %}
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
          {% for post in mc_posts limit:5 %}<li><a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></li>{% endfor %}
        </ul>
      </section>
    </aside>
  </div>
</div>
