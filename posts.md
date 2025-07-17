---
layout: page
title: All Posts
permalink: /posts/
---

# 📝 All Posts

{% if site.posts.size > 0 %}
  <div class="post-list">
    {% for post in site.posts %}
      <article class="post-item">
        <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <p class="post-meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
          {% if post.categories.size > 0 %}
            • Filed under: 
            {% for category in post.categories %}
              <span class="category">{{ category }}</span>{% unless forloop.last %}, {% endunless %}
            {% endfor %}
          {% endif %}
        </p>
        {% if post.excerpt %}
          <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
        {% endif %}
        <a href="{{ post.url | relative_url }}" class="read-more">Read more →</a>
      </article>
      {% unless forloop.last %}<hr>{% endunless %}
    {% endfor %}
  </div>
{% else %}
  <div class="no-posts">
    <p>No posts found yet. <a href="/">Return home</a> to get started!</p>
  </div>
{% endif %}
