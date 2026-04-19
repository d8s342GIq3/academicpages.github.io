---
layout: archive
title: "Blog Articles"
permalink: /blog-articles/
author_profile: true
---

{% include base_path %}

{% comment %} 
Pulling from the site.blog_articles collection 
{% endcomment %}

{% assign sorted_blogs = site.blog_articles | sort: 'date' | reversed %}

{% for post in sorted_blogs %}
  <div class="list__item">
    <article class="archive__item">
      <h2 class="archive__item-title">
        <a href="{{ post.external_link }}">{{ post.title }}</a>
      </h2>
      <p>Published — {{ post.date | date: "%B %d, %Y" }}</p>
    </article>
  </div>
{% endfor %}
