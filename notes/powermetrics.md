---
tags: [macos]
title: powermetrics
created: '2020-08-12T12:08:21.435Z'
modified: '2020-08-12T12:11:55.241Z'
---

# powermetrics

> gathers and display cpu usage statistics

## usage
```sh
powermetrics --samplers smc |grep -i "CPU die temperature"      # poll cpu temp

powermetrics --samplers smc -i1 -n1  # get a single instant sample of SMC sensor reading
```
## see also
- [[nettop]]
