---
layout: page
title: Posts
permalink: /posts/
---

<div class="post-feed">
  {% for post in site.posts %}
    <article class="post-item">
      <h2 class="post-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      <p class="post-excerpt">
        {% if post.custom_excerpt %}
          {{ post.custom_excerpt | truncate: 100 }}
        {% else %}
          {{ post.excerpt | strip_html | truncate: 100 }}
        {% endif %}
      </p>
    </article>
  {% endfor %}
</div>