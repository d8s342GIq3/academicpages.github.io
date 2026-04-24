---
layout: single
title: "Public Outreach"
permalink: /public-outreach/
author_profile: true
---

Browse my recent media appearances, podcasts, and video presentations.

<br>

{% for post in site.public_outreach %}
  {% include archive-single.html %}
{% endfor %}
