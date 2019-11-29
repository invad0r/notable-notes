---
tags: [prometheus]
title: promql
created: '2019-07-30T06:19:49.216Z'
modified: '2019-11-17T17:42:31.448Z'
---

# promql
> `prometheus query language`

## usage
```sh
topk(10, count by (__name__)({__name__=~".+"}))    # top 10 metrics

sort_desc (sum by(__name__)({name=~"afp-outbound_application.1.*"}))

sum by (__name__)({name=~"rabbitmq.*"})

time() - process_start_time_seconds{job="traefik-metrics", instance=~"$server"}   # uptime

time() - node_boot_time_seconds{instance=~"$server"}

histogram_quantile(0.$percentiles, rate(traefik_entrypoint_request_duration_seconds_bucket{code="200",method="GET"}[5m]))

sum(rate(traefik_backend_requests_total{code=~"2.."}[5m])) by (method, code)

sum by (instance) (irate(node_disk_io_time_ms{instance=~"swarm-2.node.ddev.domain.net:9100"}[5m]))
```

## api
```sh
/api/v1/label/SERVICE_NAME/values  # label which use SERVICE_NAME=".."

/api/v1/label/name/values          # labels which use name=".."

/-/reload

```
## see also
- [[promtool]]
- [Querying basics | Prometheus](https://prometheus.io/docs/prometheus/latest/querying/basics/)
- [PromQL for Humans](https://timber.io/blog/promql-for-humans/)
- [PromQL queries for the rest of us](https://www.weave.works/blog/promql-queries-for-the-rest-of-us/)
- [Prometheus: grouping metrics by metric names - Stack Overflow](https://stackoverflow.com/a/49151596)
- [Google Groups](https://groups.google.com/d/msg/prometheus-developers/oK_bx8rHmZs/0AA3lWnwAQAJ)
