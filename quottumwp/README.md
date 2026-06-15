# quottumwp — Quottum for WordPress changelog

Self-hosted [Openchangelog](https://openchangelog.com) instance for the **Quottum WordPress plugin** (Lite + Pro), deployed on Coolify at **https://changelogwp.quottum.io**.

Part of the `gaviso/openchangelog` monorepo — this folder is one product instance (built by Coolify with `base_directory: /quottumwp`).

## How it works

- `Dockerfile` — extends `ghcr.io/jonashiltl/openchangelog` and `COPY`s the config + release notes into the image.
- `docker-compose.yml` — builds the image, exposes port 6001, has a healthcheck.
- `openchangelog.yml` — site config (title, theme, etc.).
- `release-notes/` — one Markdown file per release.

## Adding a release note

Create a file in `release-notes/` with frontmatter:

```markdown
---
title: 1.2.0
description: Short summary shown in the list.
publishedAt: 2026-06-20
tags:
  - Added
  - Pro
---

Markdown body…
```

Tag **Pro** on Pro-only changes. Commit + push to `main`; Coolify rebuilds this instance (scoped via `watch_paths: quottumwp/**`).

The canonical source of truth is the GitHub Release on `gaviso/quottumwp`, which should also feed the wp.org `readme.txt` changelog and the EDD update notes.
