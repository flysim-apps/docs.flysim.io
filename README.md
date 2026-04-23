# FlyAround Documentation

Source for [docs.flysim.io](https://docs.flysim.io) — the official documentation for **FlyAround**, a flight tracking and management platform for MSFS 2020/2024, X-Plane 11/12, and Prepar3D.

Built with [Jekyll](https://jekyllrb.com/) and the [Just the Docs](https://just-the-docs.com/) theme. Deployed automatically to GitHub Pages on every push to `main`.

## Local development

```bash
bundle install
bundle exec jekyll serve
```

Open [http://localhost:4000](http://localhost:4000).

## Structure

```
index.md              # Home page
docs/                 # Documentation pages
  faq/                # FAQ section
_sass/custom/         # Theme overrides (colors, layout, typography)
_includes/            # Custom head/header partials (fonts, theme toggle)
assets/
  images/             # Screenshots and images
  js/                 # Theme toggle script
_config.yml           # Jekyll + Just the Docs configuration
```

## Adding content

Create a new `.md` file in `docs/` with this front matter:

```yaml
---
layout: default
title: Page Title
nav_order: 5
---
```

For a child page (e.g. under FAQ):

```yaml
---
layout: default
title: Page Title
nav_order: 1
parent: FAQ
---
```

Images go in `assets/images/` and are referenced as:

```markdown
![Description]({{ site.baseurl }}/assets/images/filename.png)
```

## Theming

The site supports light and dark mode via a toggle in the header. The theme is saved to `localStorage` and defaults to the user's OS preference. Color variables are defined in `_sass/custom/custom.scss`.
