---
layout: post
title: "Learning Jekyll - Setting up a jekyll project"
date: 2025-08-07
categories: learning jekyll
tags: [jekyll, markdown, liquid, posts]
---

This post summarizes important points to consider when learning Jekyll and shows the typical syntax for creating a post with Markdown.

Why Jekyll?
- Simple static site generator that converts Markdown + templates into a static website.
- Integrates well with GitHub Pages for easy deployment.

Prerequisites
- Basic knowledge of Markdown for writing content.
- Basic understanding of HTML/CSS (helpful for customizing themes).
- Command-line familiarity for running Jekyll locally (bundle exec jekyll serve).

Project structure highlights
- `_config.yml` — site configuration and plugin settings.
- `_posts/` — where blog posts go; filenames must be date-prefixed: `YYYY-MM-DD-title.md`.
- `_layouts/`, `_includes/`, `_sass/` — theme and layout files.
- `assets/` or `images/` — static assets like images, CSS, JS.

Front matter
- Every post or page that Jekyll should process needs YAML front matter between `---` lines.
- Front matter typically contains `layout`, `title`, `date`, `categories`, and `tags`.

Markdown + Liquid
- Write content in Markdown. Use Liquid tags to insert site data or control logic: `{{ site.title }}`, {% raw %}{% if page.author %}{% endraw %}.
- Example uses: include dynamic site metadata, loop through collections, or include partials.

Creating a new post (example)
Below is a minimal example of a post file you can place in `_posts/` as `2025-08-29-my-first-jekyll-post.md`:

```markdown
---
layout: post
title: "My First Jekyll Post"
date: 2025-08-06 09:00:00 +0300
categories: jekyll
tags: [tutorial, markdown]
---

## Introduction

This is a sample Jekyll post written in Markdown. Jekyll will process the YAML front matter and render this content into your site layout.

- Use headings, lists, images, and links as usual in Markdown.
- Insert Liquid variables: Site title: `{{ site.title }}`.

{% raw %}
{% include my-snippet.html %}
{% endraw %}

End of example.
```

Tips and best practices
- Keep consistent front matter fields (title, date, categories) for easier indexing and templates.
- Use `categories` and `tags` for organization — keep them predictable.
- Test locally with `bundle exec jekyll serve` to preview changes.
- When customizing themes, create a child theme or override specific layout files rather than copying the entire theme.

Further learning
- Read the official Jekyll docs: https://jekyllrb.com
- Explore Liquid templates and how to use includes and filters.

Happy building — start by creating a dated Markdown file in `_posts/` and preview locally.
