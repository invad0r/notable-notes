---
tags: [cli, prometheus]
title: promtool
created: '2019-07-30T06:19:49.218Z'
modified: '2019-08-02T09:40:13.466Z'
---

# promtool

## query via cli

```sh
promtool query instant http://prometheus.domain.net:9090 'node_memory_Cached_bytes{instance="docker-registry"}'
```

