---
layout: page
title: Welcome
permalink: /
---

# 🌿 Welcome to Amphibious9

A little corner of the internet where landscaping meets frog lore 🐸✨  
Explore my living retaining walls, blog updates, and nature magic.

---

## 🖼️ Gallery Preview

<div class="carousel">
  {% assign gallery_images = site.static_files | where_exp: "file", "file.path contains 'assets/gallery'" %}
  {% for img in gallery_images %}
    {% assign filename = img.path | split: '/' | last | split: '.' | first %}
    {% assign alt_text = filename | replace: 'Screenshot ', 'Project photo from ' | replace: '%20', ' ' %}
    <img src="{{ img.path }}" alt="{{ alt_text }}" class="slide{% if forloop.first %} active{% endif %}" loading="lazy">
  {% endfor %}
</div>

<script>
let index = 0;
const slides = document.querySelectorAll('.carousel .slide');

function rotateSlides() {
  if (slides.length === 0) return;
  
  slides[index].classList.remove('active');
  index = (index + 1) % slides.length;
  slides[index].classList.add('active');
}

// Only start rotation if we have slides
if (slides.length > 1) {
  setInterval(rotateSlides, 4000);
}
</script>

<style>
.carousel {
  max-width: 600px;
  margin: 2rem auto;
  position: relative;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0,0,0,0.15);
}

.slide {
  display: none;
  width: 100%;
  height: 350px;
  object-fit: cover;
  transition: opacity 0.5s ease-in-out;
}

.slide.active {
  display: block;
}

.post-list {
  padding-left: 0;
  list-style: none;
}

.post-list li {
  margin-bottom: 1rem;
  padding: 0.75rem;
  border-left: 3px solid #2a7f62;
  background: rgba(42, 127, 98, 0.05);
  border-radius: 0 6px 6px 0;
  transition: background-color 0.3s ease;
}

.post-list li:hover {
  background: rgba(42, 127, 98, 0.1);
}

.post-list a {
  color: #2a7f62;
  text-decoration: none;
  font-weight: 500;
}

.post-list a:hover {
  text-decoration: underline;
  color: #1e5a47;
}

.post-list small {
  color: #666;
  font-size: 0.85rem;
}

.explore-links {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
  justify-content: center;
  margin: 2rem 0;
}

.explore-links a {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  background: #2a7f62;
  color: white;
  text-decoration: none;
  border-radius: 25px;
  transition: all 0.3s ease;
  font-weight: 500;
}

.explore-links a:hover {
  background: #1e5a47;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(42, 127, 98, 0.3);
  color: white;
}

/* Responsive design */
@media (max-width: 768px) {
  .carousel {
    margin: 1rem auto;
    max-width: 90%;
  }
  
  .slide {
    height: 250px;
  }
  
  .explore-links {
    flex-direction: column;
    align-items: center;
  }
  
  .explore-links a {
    width: 200px;
    text-align: center;
  }
}
</style>

---

## 📝 Recent Blog Posts

<ul class="post-list">
  {% for post in site.posts limit:5 %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <small> — {{ post.date | date: "%B %d, %Y" }}</small>
    </li>
  {% endfor %}
</ul>

---

## 🌱 Explore

<div class="explore-links">
  <a href="/posts/">📝 All Posts</a>
  <a href="/gallery/">🖼️ Full Gallery</a>
  <a href="/about/">📜 About Me</a>
</div>
