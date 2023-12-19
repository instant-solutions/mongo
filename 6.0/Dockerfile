FROM mongo:6.0.12
LABEL authors="instant:solutions OG"

ARG HEALTHCHECK_VERSION=1.0.0
ARG TARGETOS
ARG TARGETARCH

ADD --chown=1000:1000 https://github.com/instant-solutions/mongo-healthcheck/releases/download/${HEALTHCHECK_VERSION}/mongo-healthcheck-${HEALTHCHECK_VERSION}-${TARGETOS}-${TARGETARCH}.tar.gz /tmp/healthcheck.tar.gz
RUN tar -xf /tmp/healthcheck.tar.gz -C /usr/bin/ \
    && chmod 755 /usr/bin/mongo-healthcheck \
    && chown 1000:1000 /usr/bin/mongo-healthcheck \
    && rm /tmp/healthcheck.tar.gz
