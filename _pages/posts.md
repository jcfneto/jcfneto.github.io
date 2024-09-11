---
layout: archive
author_profile: false
permalink: /posts/
title: "Posts"
# excerpt: "Thoughts"
header:
  overlay_image: https://wallpapers.com/images/high/plain-black-background-ms6uthqmbsf3weim.webp
  overlay_filter: 0.5
---

{% include base_path %}
{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
{% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
{% if year != written_year %}
<h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>
{% capture written_year %}{{ year }}{% endcapture %}
{% endif %}
{% include archive-single.html %}
{% endfor %}
