# icw1.github.io

Personal site of Ian Crowe-Wright — Senior AI Engineer.

- **Homepage** (`index.html`): a static single-page career timeline. Plain HTML/CSS/JS, no build step needed.
- **Blog** (`/blog/`): rendered by Jekyll (GitHub Pages) from Markdown posts in `_posts/`.
- **Styling**: one shared stylesheet at `assets/css/main.css`, used by both the homepage and blog layouts.

## Local preview

```sh
docker run --rm -v "$PWD:/srv/jekyll" -p 4000:4000 jekyll/jekyll:4 jekyll serve --host 0.0.0.0
```

Then open http://localhost:4000.

## Writing a post

Add a Markdown file to `_posts/` named `YYYY-MM-DD-title.md` with front matter:

```yaml
---
layout: post
published: true
title: My Post Title
---
```

Use `<!--more-->` in the body to mark where the listing excerpt ends. Set `published: false` to hide a post.

## TODO

- **CV**: not published yet. Create a new public-safe version (new format — e.g. a styled `/cv/` page
  or Notion export, with the phone number removed), save it as `assets/Ian_Crowe-Wright_CV.pdf`, and
  restore the commented-out "Download CV" button in `index.html`.
- Swap the homepage hero visualisation for a race/headshot photo when available
  (remove the `natural` class from `hero-img` for a portrait photo).
