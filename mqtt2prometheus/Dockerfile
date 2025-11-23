ARG BUILD_FROM=ghcr.io/hassio-addons/base:19.0.0
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Download and install mqtt2prometheus
ARG MQTT2PROMETHEUS_VERSION="0.1.7"
RUN wget --progress https://github.com/hikhvar/mqtt2prometheus/releases/download/v${MQTT2PROMETHEUS_VERSION}/mqtt2prometheus_${MQTT2PROMETHEUS_VERSION}_linux_amd64.apk -O /tmp/mqtt2prometheus.apk && \
    apk --no-cache add --allow-untrusted /tmp/mqtt2prometheus.apk=${MQTT2PROMETHEUS_VERSION} && \
    rm /tmp/mqtt2prometheus.apk

# Copy root filesystem
COPY rootfs /

# Health check
# HEALTHCHECK \
#     CMD curl --fail http://127.0.0.1:1337/api/health || exit 1

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_DESCRIPTION
ARG BUILD_NAME
ARG BUILD_REF
ARG BUILD_REPOSITORY
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="christian-vdz (https://github.com/christian-vdz)" \
    org.opencontainers.image.title="${BUILD_NAME}" \
    org.opencontainers.image.description="${BUILD_DESCRIPTION}" \
    org.opencontainers.image.vendor="MQTT2Prometheus Hassio add-on" \
    org.opencontainers.image.authors="christian-vdz (https://github.com/christian-vdz)" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.url="https://github.com/christian-vdz" \
    org.opencontainers.image.source="https://github.com/${BUILD_REPOSITORY}" \
    org.opencontainers.image.documentation="https://github.com/${BUILD_REPOSITORY}/blob/main/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}
