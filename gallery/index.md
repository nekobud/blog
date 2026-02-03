---
layout: page
title: Photo Gallery
permalink: /gallery/
---

# Photo Gallery

<div class="gallery">
{% for image in site.static_files %}
  {% if image.path contains 'assets/images/bonus_' and image.extname == '.jpg' %}
    <div class="gallery-item">
      <img src="{{ site.baseurl }}{{ image.path }}" alt="Gallery image" />
    </div>
  {% endif %}
{% endfor %}
</div>

<p>These images represent special moments and memories captured during various activities. From tech projects to daily life, each photo holds a special place in my digital heart.</p>

<style>
.gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.gallery-item {
  flex: 1 1 calc(33.333% - 10px);
  overflow: hidden;
}

.gallery-item img {
  width: 100%;
  height: auto;
  display: block;
}
</style>