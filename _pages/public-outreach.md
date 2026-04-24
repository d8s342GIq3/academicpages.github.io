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
    <div class="list__item" style="border-bottom: 1px solid #444; padding-bottom: 30px; margin-bottom: 30px; display: flex; align-items: center;">
      
      {% if entry.header.teaser %}
      <div style="flex: 0 0 250px; margin-right: 30px;">
          <img src="{{ entry.header.teaser }}" alt="{{ entry.title }}" style="border-radius: 8px; width: 100%; box-shadow: 0 4px 8px rgba(0,0,0,0.3);">
      </div>
      {% endif %}

      <div>
        <h2 style="margin-top: 0; border-bottom: none; font-size: 1.5em;">
          {{ entry.title | replace: " | ", ": " }}
        </h2>
        
        <p style="font-size: 0.9em; color: #999; margin-bottom: 15px;">
          <i class="fas fa-calendar-alt"></i> Published: {{ entry.date | date: "%B %d, %Y" }}
        </p>

        <div class="media-buttons">
          {% if entry.youtube_url %}
            <a href="{{ entry.youtube_url }}" class="btn btn--danger" target="_blank"><i class="fab fa-youtube"></i> YouTube</a>
          {% endif %}
          
          {% if entry.spotify_url %}
            <a href="{{ entry.spotify_url }}" class="btn btn--success" target="_blank"><i class="fab fa-spotify"></i> Spotify</a>
          {% endif %}

          {% if entry.apple_url %}
            <a href="{{ entry.apple_url }}" class="btn btn--info" target="_blank"><i class="fas fa-podcast"></i> Apple</a>
          {% endif %}
        </div>
      </div>
      
    </div>
  {% endfor %}
</div>
