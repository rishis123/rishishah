---
layout: post
title: "How to create a new blog post"
description: "A short starter guide for publishing future posts in the Jekyll workflow."
date: 2026-08-02 10:00:00 -0400
tags: [Jekyll, GitHub Pages, Markdown]
---

A simple personal blog on GitHub Pages works well with Jekyll because it is fully supported by GitHub Pages and does not require any custom server-side setup.

To create a new post:

1. Add a new Markdown file in the `_posts` directory.
2. Use the filename format `YYYY-MM-DD-title.md`.
3. Include front matter at the top with `layout`, `title`, `date`, and `tags`.
4. Write the article body in Markdown.

For example:

```markdown
---
layout: post
title: "My new post"
date: 2026-08-02 10:00:00 -0400
tags: [Engineering, Jekyll]
---

This is the body of the article.
```

You can also include inline math like $E = mc^2$ or display math:

$$
\int_0^1 x^2 \, dx = \frac{1}{3}
$$

That keeps the blog minimal, readable, and easy to publish from GitHub Pages.
