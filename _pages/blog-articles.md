---
layout: archive
title: "Blog Articles"
permalink: /blog-articles/
author_profile: true
---

{% include base_path %}

{% comment %}
We are going to manually map the dates to a string and sort that.
This is the 'heavy duty' way to force a re-order.
{% endcomment %}

{% assign blogs = site.blog_articles | sort: "date" %}

{% for post in blogs reversed %}
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
