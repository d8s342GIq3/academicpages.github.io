---
layout: archive
title: "Blog Articles"
permalink: /blog-articles/
author_profile: true
---

{% include base_path %}

{% comment %} 
This sorts by the 'date' field in your .md files 
and puts the newest at the top.
{% endcomment %}

{% assign sorted_blogs = site.blog_articles | sort: 'date' | reversed %}

{% for post in sorted_blogs %}
  <div class="list__item">
    <article class="archive__item">
      <h2 class="archive__item-title">
        <a href="{{ post.external_link }}">{{ post.title }}</a>
      </h2>
      <p>Published on <strong>{{ post.type }}</strong> — {{ post.date | date: "%B %d, %Y" }}</p>
      {% if post.excerpt %}<p>{{ post.excerpt }}</p>{% endif %}
    </article>
  </div>
{% endfor %}
