---
layout: archive
title: "Blog Articles"
permalink: /blog-articles/
author_profile: true
---

{% include base_path %}

{% assign sorted_blogs = site.data.external_blogs | sort: 'date' | reversed %}

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
