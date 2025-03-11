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
          {{ post.custom_excerpt | strip_html | truncate: 300 }}
        {% else %}
          {{ post.excerpt | strip_html | truncate: 300 }}
        {% endif %}
      </p>
      <p class="post-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">
          {{ post.date | date: "%B %d, %Y" }}
        </time>
        {% if post.categories %}
        • 
        {% for category in post.categories %}
          <span class="post-category">{{ category }}</span>
        {% endfor %}
        {% endif %}
      </p>
    </article>
  {% endfor %}
</div>