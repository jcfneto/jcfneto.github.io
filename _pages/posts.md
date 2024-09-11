---
layout: archive
author_profile: false
permalink: /posts/
title: "Posts"
# excerpt: "Thoughts"
header:
  overlay_image: https://natureconservancy-h.assetsadobe.com/is/image/content/dam/tnc/nature/en/photos/brazil/cerrado-fantini.jpg?crop=0%2C115%2C2500%2C1375&wid=4000&hei=2200&scl=0.625
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
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
