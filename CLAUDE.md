# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
hugo serve          # local dev server with live reload
hugo                # build static site to public/
hugo new posts/my-post-title.md   # create new post from archetype
```

## Architecture

This is a Hugo static site (gees.dev) using the **typo** theme (stored directly in `themes/typo/`, not a submodule).

**Key files:**
- `hugo.toml` — all site configuration (theme, params, menus, social links, breadcrumbs)
- `layouts/_default/_markup/render-link.html` — custom link renderer that opens external links in new tabs
- `archetypes/default.md` — template for new posts (TOML frontmatter, `draft = true` by default)

**Content structure:**
- `content/posts/` — blog posts in Markdown with YAML frontmatter
- `content/about.md`, `content/talks.md` — static pages

## Post frontmatter conventions

Posts use YAML frontmatter with these fields:

```yaml
---
title: "Post Title"
date: 2026-01-01
summary: "One-line summary shown in post listings"
tags: ["tag1", "tag2"]
readTime: true        # show estimated read time
autonumber: false     # auto-number headings
---
```

Posts start as drafts (`draft: true`) when created via `hugo new`. Remove or set to `false` before publishing.
