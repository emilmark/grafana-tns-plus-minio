# Docker Compose Demo

This is a modifed version of the https://github.com/grafana/tns demo. It's using docker-compose to bring up a complete stack with the demo app, including Grafana, Prometheus, Loki and Tempo.
The datasources and cross-datasource links should all be configured correctly.

The modification consists of the addition of MinIO and updated Loki configuration.

To run:

```shell
$ docker plugin install grafana/loki-docker-driver:latest --alias loki --grant-all-permissions
$ docker-compose up -d
```

The navigate to http://localhost:3000 to see Grafana.

If you have any problems, run `docker-compose up -d` first.

Optionally, [enable docker metrics](https://docs.docker.com/config/daemon/prometheus/) by adding this to your docker config:

```json
{
  "metrics-addr" : "127.0.0.1:9323",
  "experimental" : true
}
```
