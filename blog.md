---
layout: page
title: Blog Archive
permalink: /blog/
current_about: false
---

# Blog Archive

*I've saved a few older posts that I think are worth reading. They were all orginally published on Medium or the Learndot blog.*


<div class="posts">
  {% for post in site.posts %}
  <div class="post">
      <span class="post-date">{{ post.date | date_to_string }}</span>
    <h2 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h2>

    {{ post.excerpt }}
    
  </div>
  {% endfor %}
</div>


<!-- 
<div class="pagination">
  {% if paginator.next_page %}
    <a class="pagination-item older" href="{{ site.baseurl }}page{{paginator.next_page}}">Older</a>
  {% else %}
    <span class="pagination-item older">Older</span>
  {% endif %}
  {% if paginator.previous_page %}
    {% if paginator.page == 2 %}
      <a class="pagination-item newer" href="{{ site.baseurl }}">Newer</a>
    {% else %}
      <a class="pagination-item newer" href="{{ site.baseurl }}page{{paginator.previous_page}}">Newer</a>
    {% endif %}
  {% else %}
    <span class="pagination-item newer">Newer</span>
  {% endif %}
</div> -->
