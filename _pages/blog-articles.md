---
layout: archive
title: "Blog Articles"
permalink: /blog-articles/
author_profile: true
---

{% include base_path %}

{% comment %} 
Since the internal date sort is failing, we sort by 'path' (the filename).
Because your files are named YYYY-MM-DD-title.md, 
sorting by path is a perfect chronological sort.
{% endcomment %}

{% assign sorted_by_filename = site.blog_articles | sort: 'path' | reversed %}

{% for post in sorted_by_filename %}
  <div class="list__item">
    <article class="archive__item" itemscope itemtype="http://schema.org/CreativeWork">
      <h2 class="archive__item-title" itemprop="headline">
        <a href="{{ post.external_link }}" rel="permalink">{{ post.title }}</a>
      </h2>
      
      <p class="page__meta">
        <strong>Published:</strong> {{ post.date | date: "%B %d, %Y" }}
      </p>

      {% if post.excerpt %}
        <p class="archive__item-excerpt" itemprop="description">
          {{ post.excerpt | markdownify | strip_html }}
        </p>
      {% endif %}
    </article>
  </div>
{% endfor %}
