---
layout: default
title: "Posts"
permalink: /posts/
---

## Posts

<ul id="posts-list">
  {% for post in site.posts %}
    <li class="post-item" style="{% unless forloop.index0 < 10 %}display:none;{% endunless %}">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span> — {{ post.date | date: "%d %b %Y" }}</span>
    </li>
  {% endfor %}
</ul>

{% if site.posts.size > 10 %}

  <p>
    <button id="load-more">Ver mais</button>
  </p>
{% endif %}

<script>
  document.addEventListener('DOMContentLoaded', function () {
    var perPage = 10;
    var items = document.querySelectorAll('#posts-list .post-item');
    var btn = document.getElementById('load-more');
    var visible = perPage;
    if (!btn) return;
    btn.addEventListener('click', function () {
      var next = Math.min(visible + perPage, items.length);
      for (var i = visible; i < next; i++) {
        items[i].style.display = '';
      }
      visible = next;
      if (visible >= items.length) {
        btn.style.display = 'none';
      }
    });
  });
</script>
