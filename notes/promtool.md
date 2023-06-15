---
tags: [cloud]
title: promtool
created: '2019-07-30T06:19:49.218Z'
modified: '2023-05-24T08:42:35.056Z'
---

# promtool

> query promtheus via cli

## usage

```sh
promtool query instant http://prometheus.domain.net:9090 'node_memory_Cached_bytes{instance="docker-registry"}'
```

## promql

> `prometheus query language`

```sh
topk(10, count by (__name__)({__name__=~".+"}))    # top 10 metrics

sort_desc (sum by(__name__)({name=~"afp-outbound_application.1.*"}))

sum by (__name__)({name=~"rabbitmq.*"})

time() - process_start_time_seconds{job="traefik-metrics", instance=~"$server"}   # uptime

time() - node_boot_time_seconds{instance=~"$server"}

histogram_quantile(0.$percentiles, rate(traefik_entrypoint_request_duration_seconds_bucket{code="200",method="GET"}[5m]))

sum(rate(traefik_backend_requests_total{code=~"2.."}[5m])) by (method, code)

sum by (instance) (irate(node_disk_io_time_ms{instance=~"swarm-2.node.ddev.domain.net:9100"}[5m]))

rate(v range-vector)

rate(prometheus_local_storage_ingested_samples_total[5m])  179.4
```

## see also

- [[prometheus]]

