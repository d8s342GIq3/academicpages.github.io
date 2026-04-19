---
layout: archive
title: "Blog Articles"
permalink: /blog-articles/
author_profile: true
---

{% include base_path %}

{% comment %} 
Step 1: Get the collection
Step 2: Sort by date (Oldest to Newest)
Step 3: Reverse that list (Newest to Oldest)
{% endcomment %}

{% assign all_blogs = site.blog_articles | sort: 'date' %}
{% assign newest_first = all_blogs | reversed %}

{% for post in newest_first %}
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
