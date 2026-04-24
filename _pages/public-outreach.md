---
layout: single
title: "Public Outreach"
permalink: /public-outreach/
author_profile: true
---

Browse my recent media appearances, podcasts, and video presentations.

<br>

{% assign outreach = site.public_outreach | sort: 'date' | reverse %}

<div class="entries-list">
  {% for entry in outreach %}
    <div class="list__item" style="border-bottom: 1px solid #444; padding-bottom: 20px; margin-bottom: 20px; display: flex; align-items: start;">
      
      {% if entry.header.teaser %}
      <div style="flex: 0 0 200px; margin-right: 20px;">
        <a href="{{ entry.url | relative_url }}">
          <img src="{{ entry.header.teaser }}" alt="{{ entry.title }}" style="border-radius: 4px; width: 100%;">
        </a>
      </div>
      {% endif %}

      <div>
        <h2 style="margin-top: 0; border-bottom: none;">
          <a href="{{ entry.url | relative_url }}" style="text-decoration: none;">{{ entry.title | replace: " | ", ": " }}</a>
        </h2>
        <p style="font-size: 0.8em; color: #999;">
          <i class="fas fa-calendar-alt"></i> Published: {{ entry.date | date: "%B %d, %Y" }}
        </p>
      </div>
      
    </div>
  {% endfor %}
</div>
