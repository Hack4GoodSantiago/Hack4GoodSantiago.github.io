---
layout: page
title: Noticias
---

<div class="posts">
  {% for post in site.posts %}
  <div class="post">
    <h1 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h1>

    <span class="post-date">{{ post.date | date_to_string }}</span>

    {{ post.excerpt | strip_html }}
  </div>
  {% endfor %}
</div>

<div class="pagination">
  {% if site.next_page %}
    <a class="pagination-item older" href="{{ site.baseurl }}page{{site.next_page}}">Anterior</a>
  {% else %}
    <span class="pagination-item older">Anterior</span>
  {% endif %}
  {% if site.previous_page %}
    {% if site.page == 2 %}
      <a class="pagination-item newer" href="{{ site.baseurl }}">Siguiente</a>
    {% else %}
      <a class="pagination-item newer" href="{{ site.baseurl }}page{{site.previous_page}}">Siguiente</a>
    {% endif %}
  {% else %}
    <span class="pagination-item newer">Siguiente</span>
  {% endif %}
</div>
