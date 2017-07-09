FROM resin/armv7hf-debian:jessie

RUN apt-get update && \
    apt-get -y --no-install-recommends install vim postfix libfontconfig curl ca-certificates && \
    apt-get clean && \
    curl -o /tmp/grafana.deb -L https://github.com/fg2it/grafana-on-raspberry/releases/download/v4.3.2/grafana_4.3.2_armhf.deb && \
    curl -o /usr/sbin/gosu -fsSL "https://github.com/tianon/gosu/releases/download/1.9/gosu-$(dpkg --print-architecture)" && \
    chmod +x /usr/sbin/gosu && \
    apt-get remove -y curl  && \
    apt-get autoremove -y   && \
    rm -rf /var/lib/apt/lists/* && \
    dpkg -i /tmp/grafana.deb || true && \
    rm /tmp/grafana.deb


VOLUME ["/var/lib/grafana", "/var/log/grafana", "/etc/grafana"]

EXPOSE 3000

ADD ./run.sh /run.sh

ENTRYPOINT ["/run.sh"]
