---
layout: default
title: Beranda
---

<style>
.home-intro {
  margin-bottom: 35px;
}

.home-intro h1 {
  font-size: 32px;
  line-height: 1.4;
}

.home-intro p {
  font-size: 16px;
  line-height: 1.8;
}

.article-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 24px;
  margin-top: 25px;
}

.article-card {
  border: 1px solid #e5e5e5;
  border-radius: 10px;
  overflow: hidden;
  background: #fff;
}

.article-card-image {
  display: block;
}

.article-card-image img {
  display: block;
  width: 100%;
  height: auto;
  aspect-ratio: 16 / 9;
  object-fit: cover;
}

.article-card-content {
  padding: 18px;
}

.article-date {
  font-size: 13px;
  color: #777;
}

.article-card h2 {
  font-size: 20px;
  line-height: 1.4;
  margin: 12px 0;
}

.article-card h2 a {
  color: #222;
  text-decoration: none;
}

.article-card h2 a:hover {
  color: #1756a9;
}

.article-description {
  font-size: 15px;
  line-height: 1.7;
  color: #555;
}

.read-more {
  display: inline-block;
  margin-top: 12px;
  font-weight: 600;
  color: #1756a9;
  text-decoration: none;
}

@media (max-width: 600px) {
  .article-grid {
    grid-template-columns: 1fr;
  }

  .home-intro h1 {
    font-size: 26px;
  }
}
</style>

<div class="home">

  <!-- INFORMASI WEBSITE -->
  <section class="home-intro">

    <h1>Selamat Datang di Media Core</h1>

    <p>
      Media Core adalah portal informasi yang
      menyajikan berita dan artikel terbaru.
    </p>

    <p>
      Temukan berbagai informasi menarik
      seputar teknologi, bisnis, ekonomi,
      dan perkembangan dunia digital.
    </p>

  </section>

  <!-- DAFTAR ARTIKEL -->
  <section class="latest-articles">

    <h2>Artikel Terbaru</h2>

    {% assign banners = site.static_files
      | where_exp: "file", "file.path contains '/assets/images/banner-'" %}

    {% assign banner_count = banners.size %}

    <div class="article-grid">

      {% for post in site.posts %}

        {% assign selected_image = nil %}

        {% if post.image %}

          {% assign selected_image = post.image %}

        {% elsif banner_count > 0 %}

          {% assign banner_index = post.slug.size | modulo: banner_count %}
          {% assign selected_image = banners[banner_index].path %}

        {% endif %}

        <article class="article-card">

          <!-- BANNER ARTIKEL -->
          {% if selected_image %}

            <a class="article-card-image"
               href="{{ post.url | relative_url }}">

              <img
                src="{{ selected_image | relative_url }}"
                alt="{{ post.title | escape }}"
                width="1280"
                height="720"
                loading="lazy"
                decoding="async">

            </a>

          {% endif %}

          <div class="article-card-content">

            <!-- TANGGAL -->
            <time class="article-date"
                  datetime="{{ post.date | date_to_xmlschema }}">
              {{ post.date | date: "%d-%m-%Y" }}
            </time>

            <!-- JUDUL -->
            <h2>
              <a href="{{ post.url | relative_url }}">
                {{ post.title | escape }}
              </a>
            </h2>

            <!-- DESKRIPSI -->
            <p class="article-description">

              {% if post.description %}

                {{ post.description | escape }}

              {% else %}

                {{ post.excerpt | strip_html | truncatewords: 25 }}

              {% endif %}

            </p>

            <!-- TOMBOL BACA -->
            <a class="read-more"
               href="{{ post.url | relative_url }}">
              Baca Selengkapnya →
            </a>

          </div>

        </article>

      {% endfor %}

    </div>

  </section>

</div>
