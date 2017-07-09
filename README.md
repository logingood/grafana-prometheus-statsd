# Description

[Prometheus](https://prometheus.io) container for armv7h or (arm32v7), e.g. Raspberry PI, Orange PI.

Along with:

* [claymore_exporter](https://github.com/murat1985/claymore_exporter)
* [stastd_exporter](https://github.com/prometheus/statsd_exporter)
* Unofficial grafana 4.2 image [grafana-armv7h](https://github.com/fg2it/grafana-on-raspberr)

Use [docker-compose](https://docs.docker.com/compose/) tool to bring everything up.

Dockerfiles are in the according directories.

# Usage
Run docker-compose on your Raspberry PI or Orange PI (armbian or debian should be installed).

```
docker-compose up -d
```

The open http://ip_of_raspberry:3000 in your browser to access grafana. 
Other links

* http://ip_of_raspberry:9090 - prometheus
* http://ip_of_rasberry:10333 - claymore_exporter
* http://ip_of_rasberry:9102 - stasd_exporter


