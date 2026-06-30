# Sequor Robotics Research — website

The website for **Sequor Robotics Research**, presenting our research works.
Live at <https://sequor-robotics-research.github.io>.

Built with the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme
(v1.0) and hosted on GitHub Pages.

## How it works

- The **front page** (`_pages/about.md`) shows a short intro and a list of our
  research works.
- The **Research** page (`_pages/projects.md`, served at `/research/`) shows the
  full, categorized list of works.
- Each research work is a file in **`_projects/`**. A work either renders as its
  own subpage, or — if its front matter sets `redirect:` — links straight to an
  external page (arXiv, paper page, etc.).

## Adding a research work

Copy an existing file in `_projects/` and edit its front matter:

```yaml
---
layout: page
title: Your Work Title
description: One-line summary shown on the card.
img: assets/img/your-thumbnail.jpg   # optional thumbnail
importance: 1                        # lower = listed first
category: manipulation               # group on the research page
# redirect: https://arxiv.org/abs/... # set this to link out instead of a subpage
---
```

Put thumbnails/figures in `assets/img/`. Categories shown on the research page
are configured via `display_categories` in `_pages/projects.md`.

## Local preview (Docker)

```bash
docker compose up
```

Then open <http://localhost:8080>. (Requires Docker; no local Ruby needed.)

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the site
and publishes it to the `gh-pages` branch. In the repo's **Settings → Pages**,
set the publishing **source to the `gh-pages` branch**.

## License

Site content © Sequor Robotics Research. The al-folio theme is MIT licensed
(see `LICENSE`).
