---
layout: default
title: Home
---

# Welcome to My Blog

<div class="post-list">
  {% for post in site.posts %}
    <article class="post-preview">
      <h2>
        <a class="post-link" href="{{ post.url }}">{{ post.title }}</a>
      </h2>
      <div class="post-meta">
        {{ post.date | date: "%B %d, %Y" }}
      </div>
      <div class="post-excerpt">
        {{ post.excerpt }}
        <a href="{{ post.url }}">Read more &raquo;</a>
      </div>
    </article>
  {% endfor %}
</div>