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