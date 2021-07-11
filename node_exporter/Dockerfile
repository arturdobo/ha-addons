ARG BUILD_FROM
ARG BUILD_ARCH

FROM $BUILD_FROM

ENV LANG C.UTF-8

ENV NODE_EXPORTER_VERSION=1.1.2
ENV BUILD_ARCH=armv7

RUN echo "https://github.com/prometheus/node_exporter/releases/download/v${NODE_EXPORTER_VERSION}/node_exporter-${NODE_EXPORTER_VERSION}.linux-${BUILD_ARCH}.tar.gz"
RUN wget "https://github.com/prometheus/node_exporter/releases/download/v${NODE_EXPORTER_VERSION}/node_exporter-${NODE_EXPORTER_VERSION}.linux-${BUILD_ARCH}.tar.gz"
RUN tar xzf node_exporter-${NODE_EXPORTER_VERSION}.linux-${BUILD_ARCH}.tar.gz
RUN mv node_exporter-${NODE_EXPORTER_VERSION}.linux-${BUILD_ARCH}/node_exporter /usr/local/bin/
RUN rm -rf node_exporter-${NODE_EXPORTER_VERSION}.linux-${BUILD_ARCH}*

COPY rootfs /

EXPOSE 9100