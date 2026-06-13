---
layout: single
title: "Public Outreach"
permalink: /public-outreach/
author_profile: true
---

Browse my recent media appearances, podcasts, and video presentations.

<br>

{% assign outreach = site.public_outreach | sort: 'date' | reverse %}

<style>
  .outreach-item { 
    border-bottom: 1px solid #444; 
    padding-bottom: 30px; 
    margin-bottom: 30px; 
    display: flex; 
    flex-direction: row; 
    align-items: center; 
  }
  .outreach-image { flex: 0 0 250px; margin-right: 30px; }
  
  @media (max-width: 768px) {
    .outreach-item { flex-direction: column; align-items: flex-start; }
    .outreach-image { flex: 0 0 auto; width: 100%; margin-right: 0; margin-bottom: 20px; }
  }
</style>

{% assign outreach = site.public_outreach | sort: 'date' | reverse %}

<div class="entries-list">
  {% for entry in outreach %}
    {% assign primary_link = entry.youtube_url | default: entry.spotify_url | default: entry.apple_url | default: entry.link %}

    <div class="outreach-item">
      
      {% if entry.header.teaser %}
      <div class="outreach-image">
        {% if primary_link %}
          <a href="{{ primary_link }}" target="_blank" rel="noopener noreferrer">
            <img src="{{ entry.header.teaser }}" alt="{{ entry.title }}" style="border-radius: 8px; width: 100%; box-shadow: 0 4px 8px rgba(0,0,0,0.3);">
          </a>
        {% else %}
          <img src="{{ entry.header.teaser }}" alt="{{ entry.title }}" style="border-radius: 8px; width: 100%; box-shadow: 0 4px 8px rgba(0,0,0,0.3);">
        {% endif %}
      </div>
      {% endif %}

      <div class="outreach-content">
        <h2 style="margin-top: 0; border-bottom: none; font-size: 1.5em;">
          {% if primary_link %}
            <a href="{{ primary_link }}" target="_blank" rel="noopener noreferrer" style="text-decoration: none; color: inherit;">
              {{ entry.title | replace: " | ", ": " }}
            </a>
          {% else %}
            {{ entry.title | replace: " | ", ": " }}
          {% endif %}
        </h2>
        
        <p style="font-size: 0.9em; color: #999; margin-bottom: 15px;">
          <i class="fas fa-calendar-alt"></i> Published: {{ entry.date | date: "%B %d, %Y" }}
        </p>

        <div class="media-buttons">
          {% if entry.youtube_url %}
            <a href="{{ entry.youtube_url }}" class="btn btn--danger" target="_blank" rel="noopener noreferrer"><i class="fab fa-youtube"></i> YouTube</a>
          {% endif %}
          
          {% if entry.spotify_url %}
            <a href="{{ entry.spotify_url }}" class="btn btn--success" target="_blank" rel="noopener noreferrer"><i class="fab fa-spotify"></i> Spotify</a>
          {% endif %}

          {% if entry.apple_url %}
            <a href="{{ entry.apple_url }}" class="btn btn--info" target="_blank" rel="noopener noreferrer"><i class="fas fa-podcast"></i> Apple</a>
          {% endif %}
        </div>
      </div>
      
    </div> {% endfor %}
</div>
