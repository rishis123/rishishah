# Publishing a new article

Send the agent a Markdown (`.md`) file and any local images it uses. You do not need to edit the homepage or prepare Jekyll metadata yourself.

## Simple handoff

1. Supply the Markdown draft and its image files, keeping their filenames or folder structure so references can be matched.
2. The agent puts the article in `_posts/YYYY-MM-DD-your-title.md`, adds minimal front matter if absent, and preserves existing metadata. Supply a title or publication date if you have a preference.
3. The agent copies local images into an article-specific folder such as `images/your-title/` and fixes their paths for the site's `/rishishah` base URL. External links and hosted images can remain URLs.
4. The agent builds the site with Jekyll and previews the Writing tab, article, links, and images for review.
5. After you approve publishing, the agent commits and pushes. Sending a draft alone does not authorize publication.

The homepage Writing tab and `/blog/` automatically list published posts from `site.posts`, newest first. No manual `index.html` changes are needed for future articles. Future-dated posts and posts marked `published: false` are not shown in a normal build.

## Metadata

Existing metadata-rich posts remain supported. A minimal article starts with:

```yaml
---
layout: post
title: "My Article Title"
---
```

The date can come from the filename. Optional `description`, `date`, and `tags` fields can also be supplied. Listings use the description when present, otherwise a short plain-text excerpt of the article.

## Links and images

Write ordinary Markdown:

```markdown
[A useful reference](https://example.com)

![A description of the image](photo.jpg)
```

Include `photo.jpg` with the draft. Once the image is copied into the site, the agent rewrites its reference using Jekyll's `relative_url` filter:

```markdown
![A description of the image]({{ '/images/your-title/photo.jpg' | relative_url }})
```

The filter makes the path work both in local previews and on GitHub Pages. Use descriptive alt text for images.

## Previewing

Use the existing Gemfile with `bundle install`, then `bundle exec jekyll serve`. With the repository configuration, the preview is at `http://127.0.0.1:4000/rishishah/`. To serve at the root instead, use `bundle exec jekyll serve --baseurl ""`.

Do not serve the source directory with a plain static file server: Jekyll must render the homepage's post list and generate article routes. Article pages use the existing shared post layout.
