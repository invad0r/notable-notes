---
tags: [prometheus]
title: promtool
created: '2019-07-30T06:19:49.218Z'
modified: '2019-11-17T17:42:17.227Z'
---

# promtool

> query promtheus via cli

## usage
```sh
promtool query instant http://prometheus.domain.net:9090 'node_memory_Cached_bytes{instance="docker-registry"}'
```

## see also
- [[promql]]

