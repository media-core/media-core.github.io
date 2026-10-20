---
layout: page
title: "Semua Artikel"
permalink: /artikel/
---

<style>
.mc-archive-intro { line-height: 1.7; color: #555; }
.mc-archive-month { margin: 30px 0; scroll-margin-top: 20px; }
.mc-archive-month h2 { margin: 0 0 10px; padding-bottom: 10px; border-bottom: 2px solid #1756a9; font-size: 23px; }
.mc-archive-list { list-style: none; margin: 0; padding: 0; }
.mc-archive-list li { padding: 14px 0; border-bottom: 1px solid #eee; }
.mc-archive-list time { display: block; margin-bottom: 5px; color: #777; font-size: 13px; }
.mc-archive-list a { color: #1756a9; font-weight: 600; text-decoration: none; }
.mc-archive-list a:hover { text-decoration: underline; }
</style>

<p class="mc-archive-intro">Jelajahi seluruh artikel Media Core berdasarkan bulan penerbitan.</p>

{% assign mc_posts = site.posts | sort: 'date' | reverse %}
{% assign previous_month = '' %}
{% assign month_names = 'Januari,Februari,Maret,April,Mei,Juni,Juli,Agustus,September,Oktober,November,Desember' | split: ',' %}

{% for post in mc_posts %}
  {% assign current_month = post.date | date: '%Y-%m' %}
  {% if current_month != previous_month %}
    {% unless previous_month == '' %}
      </ul>
      </section>
    {% endunless %}
    {% assign month_number = post.date | date: '%-m' %}
    {% assign month_index = month_number | minus: 1 %}
    <section class="mc-archive-month" id="bulan-{{ current_month }}">
      <h2>{{ month_names[month_index] }} {{ post.date | date: '%Y' }}</h2>
      <ul class="mc-archive-list">
    {% assign previous_month = current_month %}
  {% endif %}
  <li>
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%d-%m-%Y' }}</time>
    <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
  </li>
{% endfor %}

{% unless previous_month == '' %}
  </ul>
  </section>
{% else %}
  <p>Belum ada artikel yang diterbitkan.</p>
{% endunless %}
