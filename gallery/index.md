---
layout: page
title: Photo Gallery
permalink: /gallery/
---

# Photo Gallery

<div class="gallery">
{% assign sorted_images = site.static_files | where_exp:"item", "item.path contains 'assets/images/bonus_' and item.extname == '.jpg'" | sort:"modified_time" | reverse %}
{% for image in sorted_images limit:12 %}
  <div class="gallery-item">
    <img src="{{ site.baseurl }}{{ image.path }}" alt="Gallery image" />
  </div>
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