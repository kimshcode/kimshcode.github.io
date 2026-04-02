---
layout: default
title: Home
---

<div class="hero">
  <p class="eyebrow">Overview</p>
  <h1>{{ site.title }}</h1>
</div>

{% for post in site.posts %}
<article class="post-card">
  <div class="post-card-top">
    <p class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</p>
    {% if post.categories and post.categories.size > 0 %}
    <p class="post-chip"><a href="{{ '/' | append: post.categories[0] | append: '/' | relative_url }}">{{ post.categories[0] | capitalize }}</a></p>
    {% endif %}
  </div>
  <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
  <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
</article>
{% endfor %}
