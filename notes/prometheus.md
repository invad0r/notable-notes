---
title: prometheus
created: '2019-11-17T17:42:41.438Z'
modified: '2019-11-17T17:59:18.211Z'
---

# prometheus

## capacity planing
```sh
needed_disk_space = retention_time_seconds * ingested_samples_per_second * bytes_per_sample


--storage.tsdb.retention.time=183d => 15811200 s

rate(prometheus_local_storage_ingested_samples_total[5m])  179.4

average, Prometheus uses only around 1-2 bytes per sample.

15811200 * 179.4 * 2 = 5 673 058 560.0 bytes
```

## functions
```sh
rate(v range-vector)
```

## see also
- https://prometheus.io/docs/prometheus/latest/storage/
