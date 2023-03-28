---
title: prometheus
created: '2019-11-17T17:42:41.438Z'
modified: '2023-03-27T05:50:15.430Z'
---

# prometheus

## usage

```sh
# capacity planing
# needed_disk_space = retention_time_seconds * ingested_samples_per_second * bytes_per_sample
# average, Prometheus uses only around 1-2 bytes per sample
# 15811200 * 179.4 * 2 = 5 673 058 560.0 bytes

--storage.tsdb.retention.time=183d => 15811200 s
```

## usage

```sh
prometheus
```

## api

```sh
GET /api/v1/label/SERVICE_NAME/values  # label which use SERVICE_NAME=".."

GET /api/v1/label/name/values          # labels which use name=".."

GET /-/reload
```

## see also

- [[promtool]]
- [prometheus.io/docs/prometheus/latest/querying/basics](https://prometheus.io/docs/prometheus/latest/querying/basics/)
- [timber.io/blog/promql-for-humans](https://timber.io/blog/promql-for-humans/)
- [eave.works/blog/promql-queries-for-the-rest-of-us](https://www.weave.works/blog/promql-queries-for-the-rest-of-us/)
- [Prometheus: grouping metrics by metric names - Stack Overflow](https://stackoverflow.com/a/49151596)
- [Google Groups](https://groups.google.com/d/msg/prometheus-developers/oK_bx8rHmZs/0AA3lWnwAQAJ)
- [prometheus.io/docs/prometheus/latest/storage/](https://prometheus.io/docs/prometheus/latest/storage/)
