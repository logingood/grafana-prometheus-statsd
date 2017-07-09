FROM resin/armv7hf-debian-qemu

ENV DEBIAN_FRONTEND noninteractive
ENV STATSD_EXPORTER_VERSION 0.4.0

RUN apt-get update && \
    apt-get install -yq \
            curl

RUN curl -Ls https://github.com/prometheus/statsd_exporter/releases/download/v$STATSD_EXPORTER_VERSION/statsd_exporter-$STATSD_EXPORTER_VERSION.linux-armv7.tar.gz | tar -xzC /tmp/ && \
    cd /tmp/statsd_exporter-$STATSD_EXPORTER_VERSION.linux-armv7 && \
    mv statsd_exporter /bin/statsd_exporter && \
    cd /tmp && rm -rf statsd_exporter-$STATSD_EXPORTER_VERSION.linux-armv7

VOLUME     [ "/metrics", "/statsd.conf" ]
WORKDIR    /prometheus/metrics
ENTRYPOINT [ "/bin/statsd_exporter" ]
CMD	   [ "-statsd.mapping-config=/statsd.conf"]
