# changelog

Self-hosted changelog powered by [Openchangelog](https://openchangelog.com), deployed on Coolify (Blackstone / Hetzner) at **https://changelog.gaviso.one**.

## How it works

- `Dockerfile` — extends `ghcr.io/jonashiltl/openchangelog` and `COPY`s the config + release notes into the image. (Coolify rewrites compose bind-mounts to its own storage paths, so the content is baked into the image instead of mounted at runtime.)
- `docker-compose.yml` — builds the image above and exposes port 6001.
- `openchangelog.yml` — site config (title, color scheme, etc.). Lands at container `/etc/openchangelog.yml`.
- `release-notes/` — one Markdown file per release. Lands at container `/release-notes`.

No database. State is this repo — every change ships by rebuilding the image.

## Adding a release note

Create a new file in `release-notes/` with frontmatter:

```markdown
---
title: Release 1.2.0
description: Short summary shown in listings.
publishedAt: 2026-06-13
tags:
  - Feature
---

Markdown body…
```

`publishedAt` is ISO 8601. Commit + push to `main`; Coolify redeploys and the entry appears.

## Deploy

Coolify watches `main`. Push to redeploy, or trigger a manual deploy from the Coolify dashboard.
