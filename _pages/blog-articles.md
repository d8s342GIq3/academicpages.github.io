---
layout: archive
title: "Blog Articles"
permalink: /blog-articles/
author_profile: true
---

{% include base_path %}

{% comment %} 
We create a variable for the collection and sort it explicitly by date.
{% endcomment %}

{% assign posts = site.blog_articles | sort: "date" | reversed %}

{% for post in posts %}
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
