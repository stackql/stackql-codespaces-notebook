FROM stackql/stackql:latest AS stackql
FROM mcr.microsoft.com/devcontainers/universal:2
COPY --from=stackql /srv/stackql/stackql /usr/local/bin/stackql