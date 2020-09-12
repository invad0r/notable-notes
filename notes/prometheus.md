---
title: prometheus
created: '2019-11-17T17:42:41.438Z'
modified: '2020-09-02T18:13:18.172Z'
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
```promql
rate(v range-vector)

rate(prometheus_local_storage_ingested_samples_total[5m])  179.4
```

## see also
- [prometheus.io/docs/prometheus/latest/storage/](https://prometheus.io/docs/prometheus/latest/storage/)
