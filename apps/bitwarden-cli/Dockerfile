FROM ghcr.io/joryirving/alpine:3.19.1

# renovate: datasource=npm depName=@bitwarden/cli versioning=npm
ARG BW_VERSION=2024.2.1

ARG TARGETPLATFORM
ARG TARGETARCH
ARG TARGETOS

LABEL dev.joryirving.image.target_platform=$TARGETPLATFORM
LABEL dev.joryirving.image.target_architecture=$TARGETARCH
LABEL dev.joryirving.image.target_os=$TARGETOS
LABEL org.opencontainers.image.source="https://github.com/bitwarden/clients"

WORKDIR /usr/local/bin

RUN \
  apk add --no-cache npm argon2-libs python3 \
  && npm i -g @bitwarden/cli@${BW_VERSION}

COPY ./entrypoint.sh /entrypoint.sh
CMD ["/entrypoint.sh"]
