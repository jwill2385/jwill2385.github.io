---
layout: page
title: blog
permalink: /blog/
description: Personal reflections, experiences, and insights from my journey in technology and entrepreneurship.
nav: true
nav_order: 5
---

<div class="posts">
  {% for post in site.posts %}
    <div class="post-preview">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p class="post-meta">{{ post.date | date: '%B %d, %Y' }}</p>
      {% if post.description %}
        <p>{{ post.description }}</p>
      {% else %}
        <p>{{ post.content | strip_html | truncatewords: 40 }}</p>
      {% endif %}
      
      <div class="post-tags">
        {% for tag in post.tags %}
          <span class="badge badge-pill badge-light">{{ tag }}</span>
        {% endfor %}
      </div>
      
      <hr>
    </div>
  {% endfor %}
</div>

{% if site.posts.size == 0 %}

  <p>No blog posts yet. Check back soon!</p>
{% endif %}
