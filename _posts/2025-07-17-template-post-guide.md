---
title: "[TEMPLATE] How to Write a Blog Post"
date: 2025-07-17 09:00:00 +1000
categories: [guides, blogging]
tags: [template, how-to, chirpy, tutorial]
pin: true
comments: true
thumbnail: /assets/img/posts/template-thumb.jpg
---

> 🐸 This post teaches you how to create your own blog post.  
> It **is** a post and also a **template**. Copy this file to start.

---

## 🧱 1. File Naming

All posts live in `_posts/`  
Filename must follow this format:

```
YYYY-MM-DD-title-of-post.md
```

📌 This post is named:  
`_posts/2025-07-17-template-post-guide.md`

---

## 📋 2. Front Matter

This block at the top tells Jekyll/Chirpy how to display your post.

```yaml
---
title: "My Amazing Post Title"
date: 2025-07-17 09:00:00 +1000
categories: [main-topic, optional-subtopic]
tags: [keyword1, keyword2]
pin: false
comments: true
thumbnail: /assets/img/posts/my-thumb.jpg
---
```

**Breakdown:**

| Field       | Description |
|-------------|-------------|
| `title`     | Main title |
| `date`      | Date/time for ordering |
| `categories`| Primary category list |
| `tags`      | Tag keywords for search |
| `pin`       | `true` will "stick" this post at the top |
| `comments`  | Enables Giscus/Disqus/etc |
| `thumbnail` | Path to image (used in previews) |

---

## 🖼️ 3. Thumbnails & Images

Place images inside `/assets/img/posts/`  
- Thumbnails should be ~800×400 or square  
- Use web-optimized JPEG/PNG

Use Markdown for inline images:

```markdown
![Alt text](/assets/img/posts/my-image.jpg)
```

To center + resize:

```html
<p align="center">
  <img src="/assets/img/posts/my-image.jpg" alt="Description of image" width="400"/>
</p>
```

---

## 🐸 4. Markdown Content

You can use:

### Headers

```markdown
## This is an H2
### This is an H3
```

### Bold, Italic, Lists

```markdown
**bold**, *italic*, `code`
- bullet
1. numbered
```

### Blockquotes

```markdown
> This is a quote.
```

### Code Blocks

<pre>
```python
def frog():
    return "ribbit"
```
</pre>

---

## 🔖 5. Tags & Categories

Chirpy shows:

- **Tags** in the sidebar & search
- **Categories** for organization (can be nested)

Use sensible lowercase tags like:

```yaml
tags: [art, frogs, updates]
categories: [life, frogs]
```

---

## 🚀 6. Publishing

Once your post is saved to `_posts/`:

```bash
git add _posts/2025-07-17-my-post.md
git commit -m "add new post"
git push
```

Chirpy will auto-rebuild your site via GitHub Pages Actions.

---

## ✅ 7. Final Checklist

- [ ] Filename is in `YYYY-MM-DD-title.md` format  
- [ ] Front matter exists and is valid YAML  
- [ ] At least one `category` and `tag`  
- [ ] Thumbnail is placed in `/assets/img/posts/`  
- [ ] Post added to `_posts/` folder  
- [ ] You pushed it to GitHub

---

## 🐸 8. Example Thumbnail Display

Here's how this post's thumbnail might appear:

<p align="center">
  <img src="/assets/img/posts/template-thumb.jpg" alt="Template post thumbnail showing blog post guide" width="300" />
</p>

---

> Feel free to copy this file as your starting point for each post.  
> Delete sections that aren't needed—this is just a guide.