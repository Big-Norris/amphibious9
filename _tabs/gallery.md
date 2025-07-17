---
title: Gallery
icon: fas fa-images
order: 3
---

# 🖼️ Project Gallery

Here's a showcase of my landscaping projects and retaining wall work:

<div class="gallery-grid">
{% for img in site.static_files %}
  {% if img.path contains 'assets/gallery' %}
    {% assign filename = img.path | split: '/' | last | split: '.' | first %}
    {% assign alt_text = filename | replace: 'Screenshot ', 'Project photo from ' | replace: '%20', ' ' %}
    <div class="gallery-item">
      <a href="{{ img.path }}" class="popup img-link">
        <img src="{{ img.path }}" alt="{{ alt_text }}" loading="lazy" />
      </a>
    </div>
  {% endif %}
{% endfor %}
</div>

<style>
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
  margin: 2rem 0;
}

.gallery-item {
  position: relative;
  overflow: hidden;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.gallery-item:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0,0,0,0.15);
}

.gallery-item img {
  width: 100%;
  height: 250px;
  object-fit: cover;
  display: block;
}

.gallery-item a {
  display: block;
  text-decoration: none;
}

@media (max-width: 768px) {
  .gallery-grid {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 0.5rem;
  }
  
  .gallery-item img {
    height: 200px;
  }
}
</style>
