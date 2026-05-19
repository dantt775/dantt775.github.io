---
layout: page
title: "Posts"
permalink: /posts/
pagination:
  enabled: true
---

## Posts

<ul>
  {% for post in paginator.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span> — {{ post.date | date: "%d %b %Y" }}</span>
    </li>
  {% endfor %}
</ul>

{% if paginator.next_page %}
  <p>
    <a class="button" href="{{ paginator.next_page_path | relative_url }}">Ver mais</a>
  </p>
{% endif %}
