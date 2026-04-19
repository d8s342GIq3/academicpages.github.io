---
layout: archive
title: "Blog Articles"
permalink: /blog-articles/
author_profile: true
---

{% include base_path %}

{% comment %} 
We assign the data to a variable, then sort by date, then reverse it.
{% endcomment %}

{% assign my_blogs = site.data.external_blogs %}
{% assign sorted_blogs = my_blogs | sort: 'date' | reversed %}

{% for post in sorted_blogs %}
  <div class="list__item">
    <article class="archive__item">
      <h2 class="archive__item-title">
        <a href="{{ post.link }}">{{ post.title }}</a>
      </h2>
      <p>Published on <strong>{{ post.venue }}</strong> — {{ post.date | date: "%B %d, %Y" }}</p>
      {% if post.excerpt %}<p>{{ post.excerpt }}</p>{% endif %}
    </article>
  </div>
{% endfor %}
