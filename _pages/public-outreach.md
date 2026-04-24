---
layout: single
title: "Public Outreach"
permalink: /public-outreach/
author_profile: true
---

Browse my recent media appearances, podcasts, and video presentations.

<br>

{% assign outreach = site.public_outreach | sort: 'date' | reverse %}
{% for entry in outreach %}
  {% include archive-single.html %}
{% endfor %}
