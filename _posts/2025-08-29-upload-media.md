---
layout: post
title: "Upload & Embed Images and Videos in Jekyll — Quick Guide"
date: 2025-08-29 13:00:00 +0300
categories: jekyll media
tags: [image, video, assets]
---

Short direct instructions for adding and embedding media in a Jekyll site.

1) Where to put files
- Images: put files under `assets/img/` (e.g. `assets/img/my-photo.jpg`).
- Videos: put files under `assets/video/` or `assets/media/` (e.g. `assets/video/demo.mp4`).

2) Image example (Markdown + Liquid)
```markdown
![My photo]({{ "/assets/img/my-photo.jpg" | relative_url }})
```
Notes: use descriptive alt text. For responsive images use `srcset` HTML or CSS classes from your theme.

HTML example with srcset:
```html
<img src="{{ '/assets/img/photo-800.jpg' | relative_url }}"
     srcset="{{ '/assets/img/photo-400.jpg' | relative_url }} 400w, {{ '/assets/img/photo-800.jpg' | relative_url }} 800w"
     sizes="(max-width: 600px) 100vw, 600px"
     alt="Short description">
```

3) Video example (local file)
```html
<video controls preload="metadata" width="720">
  <source src="{{ '/assets/video/sample.mp4' | relative_url }}" type="video/mp4">
  <!-- Optional WebM fallback -->
  <source src="{{ '/assets/video/sample.webm' | relative_url }}" type="video/webm">
  Your browser does not support the video tag.
</video>
```
Tips: keep videos optimized for web (H.264/AAC MP4), add multiple formats if needed, and set a small poster image if desired: `poster="{{ '/assets/img/video-poster.jpg' | relative_url }}`.

4) Video example (YouTube embed)
```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID" title="YouTube video" frameborder="0" allowfullscreen></iframe>
```
Use external hosting for large files or when you want streaming + bandwidth savings.

5) Build & preview
- Commit the media files to the repository (or store them externally).
- Run `bundle exec jekyll serve` and visit `http://localhost:4000` to preview.

6) Notes & best practices
- Avoid committing very large videos to GitHub; use external hosting (YouTube, Vimeo, S3) or Git LFS.
- Keep filenames simple and lowercase with dashes; update references if you move files.
- For accessibility add `alt` text for images and captions/transcripts for videos when appropriate.

That's it — add your files to `assets/img/` or `assets/video/`, reference them with `relative_url`, and preview locally.
