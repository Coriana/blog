---
layout: default
title: Home
---

# Welcome to My Blog

<div class="post-list">
  {% for post in site.posts %}
    <article class="post-preview">
      <h2>
        <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      <div class="post-meta">
        {{ post.date | date: "%B %d, %Y" }}
      </div>
      {% if post.excerpt %}
        <div class="post-excerpt">
          {{ post.excerpt }}
        </div>
      {% endif %}
    </article>
  {% endfor %}
</div>