FROM stackql/stackql:latest AS stackql
FROM mcr.microsoft.com/devcontainers/universal:2
COPY --from=stackql /srv/stackql/stackql /usr/local/bin/stackql
RUN stackql exec 'registry pull aws' || (echo "Failed to pull aws provider" && exit 1)
RUN stackql exec 'registry pull google' || (echo "Failed to pull google provider" && exit 1)
RUN stackql exec 'registry pull github' || (echo "Failed to pull github provider" && exit 1)