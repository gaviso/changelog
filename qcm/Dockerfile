FROM ghcr.io/jonashiltl/openchangelog:0.6.2

# Bake config + release notes into the image (Coolify rewrites compose
# bind-mounts to its own storage paths, so runtime mounts of repo files
# don't reach the container).
COPY openchangelog.yml /etc/openchangelog.yml
COPY release-notes /release-notes
