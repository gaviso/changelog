# Gaviso QCM — changelog

Self-hosted [Openchangelog](https://openchangelog.com) for **Gaviso QCM**, served at
**https://changelog.qcm.gaviso.agency**.

- Add an entry: commit a markdown file to `release-notes/` with frontmatter
  `{title, description, publishedAt (ISO 8601), tags}`. A push to `main` auto-redeploys.
- Config: `openchangelog.yml` (baked into the image via the `Dockerfile`).
- Deploy: docker-compose app on Coolify (project *Openchangelog*), behind Let's Encrypt.
