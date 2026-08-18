---
permalink: /
title: "Hello!"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a PhD Candidate and Research Assistant at the Royal College of Surgeons in Ireland, based within the Centre for Positive Health Sciences. My background is an MSci in Psychology with a specialisation in Neuroscience and Neuroimaging, and my research sits at the intersection between positive psychology and environmental psychology.

In my PhD I investigate the psychological and physiological benefits of engaging with nature, specifically through activities like forest therapy, stargazing, and cloudspotting. I am interested in how these experiences evoke awe and lead to transformation. My work is inspired by humanistic psychology and driven by my belief in human goodness.

Beyond my primary research, my academic interests extend to storytelling, death and mortality awareness, virtues, psychedelics, and many more. Originally from Slovakia 🇸🇰 and now based in Dublin, I am looking forward to understanding how these experiences help people flourish.

## 📖 Currently Reading

{% if site.data.currently_reading %}
<div style="display: flex; align-items: center; gap: 16px; background: rgba(255, 255, 255, 0.04); border: 1px solid rgba(255, 255, 255, 0.1); padding: 14px; border-radius: 8px; margin-top: 15px;">
  {% if site.data.currently_reading.cover %}
  <img src="{{ site.data.currently_reading.cover }}" alt="Book cover" style="width: 75px; height: auto; border-radius: 4px; flex-shrink: 0; box-shadow: 0 4px 8px rgba(0,0,0,0.3);">
  {% endif %}
  <div>
    <h4 style="margin: 0 0 4px 0; font-size: 1em;">
      {% if site.data.currently_reading.link %}
        <a href="{{ site.data.currently_reading.link }}" target="_blank" rel="noopener" style="color: #f1d279; text-decoration: none;">{{ site.data.currently_reading.title }}</a>
      {% else %}
        {{ site.data.currently_reading.title }}
      {% endif %}
    </h4>
    <p style="margin: 0; font-size: 0.88em; opacity: 0.85; color: #d0d0d0;">
      by {{ site.data.currently_reading.author }}
    </p>
  </div>
</div>
{% endif %}
