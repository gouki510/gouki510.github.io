---
layout: page
permalink: /blog/
title: blog
nav: true
nav_order: 3
---

<div class="post">

  <div class="header-bar">
    <h1>{{ site.blog_name }}</h1>
    <h2>{{ site.blog_description }}</h2>
  </div>

  {% if site.posts.size > 0 %}
  <ul class="post-list">
    {% for post in site.posts %}
    {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
    <li>
      <h3>
        <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      <p>{{ post.description }}</p>
      <p class="post-meta">
        {{ read_time }} min read &nbsp; &middot; &nbsp;
        {{ post.date | date: '%B %d, %Y' }}
      </p>
    </li>
    {% endfor %}
  </ul>
  {% else %}
  <p style="text-align: center; color: var(--global-text-color-light); margin-top: 3rem;">
    Coming soon...
  </p>
  {% endif %}

</div>
