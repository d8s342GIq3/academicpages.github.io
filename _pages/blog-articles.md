---
layout: archive
title: "Blog Articles"
permalink: /blog-articles/
author_profile: true
---

{% include base_path %}

{% comment %} 
We sort the collection by date. If 'reversed' isn't working, 
we ensure the date format in your files is YYYY-MM-DD.
{% endcomment %}

{% assign sorted_blogs = site.blog_articles | sort: 'date' | reversed %}

{% for post in sorted_blogs %}
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
