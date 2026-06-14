# Gaviso Openchangelog

Umbrella repo for the self-hosted [Openchangelog](https://openchangelog.com) instances.
Each product changelog is a subfolder built as its own Coolify app (set the app's
**Base Directory** to the subfolder):

| Subfolder | Site | Coolify base dir |
|---|---|---|
| `membership/` | https://changelog.gaviso.one | `/membership` |
| `qcm/` | https://changelog.qcm.gaviso.agency | `/qcm` |

Add an entry: commit a markdown file to `<product>/release-notes/` with frontmatter
`{title, description, publishedAt, tags}`.
