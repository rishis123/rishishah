# Publishing a new article

This site is designed to keep the homepage static and let Jekyll handle the blog.

## Workflow

1. Create a new Markdown file in `_posts/`.
2. Use the filename format `YYYY-MM-DD-your-title.md`.
3. Add front matter at the top:

```markdown
---
layout: post
title: "My Article Title"
description: "One-line summary for the blog index"
date: 2026-08-02 10:00:00 -0400
tags: [Engineering, Research]
---
```

4. Write the article body in Markdown.
5. Commit and push.

## Notes

- The homepage stays in `index.html`.
- The Writing nav item points to `/blog/`.
- The `/blog/` page is generated from `site.posts` automatically.
- Article pages are rendered through the shared Jekyll post layout.
- If you need math, use KaTeX-style delimiters like `$...$` and `$$...$$`.
