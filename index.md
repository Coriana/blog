---
layout: default
title: Home
---

# Welcome to My Blog

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url | prepend: site.baseurl }})
  <small>{{ post.date | date: "%B %d, %Y" }}</small>
{% endfor %}