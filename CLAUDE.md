# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Static documentation site for **FlyAround** — a flight tracking and management platform for Microsoft Flight Simulator 2020/2024, X-Plane 11/12, and Prepar3D. Built with Jekyll and the [Just the Docs](https://just-the-docs.com/) theme, deployed to [docs.flysim.io](https://docs.flysim.io) via GitHub Pages.

## Local development

```bash
bundle install          # first time only
bundle exec jekyll serve
```

The site is served at `http://localhost:4000`. GitHub Pages handles deployment automatically on push to `main`.

## Site structure

- `index.md` — home page (`layout: home`)
- `docs/` — all documentation pages (`layout: default`)
- `docs/faq/` — FAQ subsection with its own `index.md` acting as the parent
- `_config.yml` — theme, plugins, search, callout colours, nav settings

## Front matter conventions

Every page in `docs/` requires:
```yaml
---
layout: default
title: Page Title
nav_order: <integer>          # controls sidebar order
parent: Parent Title          # if this is a child page (e.g. under "Features" or "FAQ")
---
```

The home page (`index.md`) uses `layout: home` and `nav_order: 1`.

Child pages reference `parent:` by the exact `title:` string of the parent page. The parent page does not need any special configuration beyond its own front matter.

## Just the Docs callouts

Use the defined callout types (configured in `_config.yml`) as block-level annotations:

```markdown
{: .note }
Text here.

{: .important }
Text here.

{: .warning }
Text here.
```

Available types: `highlight`, `important`, `new`, `note`, `warning`.

## Content style

- Pages use `{: .no_toc }` on the `h1` and a TOC block when sections are long
- Tables are used for structured reference data (keyboard shortcuts, field descriptions, etc.)
- Section headings link to related pages using `{% link docs/page-name.md %}`
- Feature subsections inside `docs/` use `parent: Features`; FAQ pages use `parent: FAQ`
