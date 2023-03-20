---
tags: [dns]
title: rndc
created: '2020-07-22T08:47:45.145Z'
modified: '2023-03-20T08:55:56.348Z'
---

# rndc

> administer the named service

## usage

```sh
rndc status

rndc dumpdb -zones

rndc freeze home.lan
rndc freeze 10.168.192.in-addr.arpa

rndc thaw home.lan
rndc thaw 10.168.192.in-addr.arpa
```

## see also

- [[named]]
- [[BIND]]
- [[dig]]

