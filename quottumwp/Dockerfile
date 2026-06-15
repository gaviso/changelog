FROM ghcr.io/jonashiltl/openchangelog:0.6.2

# Bake the config and release notes into the image so the content is
# versioned in this repo (Coolify rewrites compose bind-mounts to its own
# persistent-storage paths, so mounting repo files at runtime does not work).
COPY openchangelog.yml /etc/openchangelog.yml
COPY release-notes /release-notes
