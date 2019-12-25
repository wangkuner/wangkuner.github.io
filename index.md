---
title: Wang Kun
---
# Building...
<ul>
  {% for post in site.posts %}
    <li>
      {% assign date_format = site.cayman-blog.date_format | default: "%b %-d, %Y" %}
        <span class="post-meta">{{ post.date | date: date_format }}</span>

      <h2>
        <a href="{{ post.url }}">{{ post.title }}</a>
      </h2>
      <!-- {{ post.excerpt }} -->
    </li>
  {% endfor %}
</ul>


