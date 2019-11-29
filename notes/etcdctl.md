---
title: etcdctl
created: '2019-09-24T04:24:49.035Z'
modified: '2019-09-24T04:25:49.203Z'
---

# etcdctl

## usage
```sh
export ETCDCTL_API=3
HOST_1=10.240.0.17
HOST_2=10.240.0.18
HOST_3=10.240.0.19
ENDPOINTS=$HOST_1:2379,$HOST_2:2379,$HOST_3:2379

etcdctl --endpoints=$ENDPOINTS member list

etcdctl --endpoints=$ENDPOINTS put foo "Hello World!"
etcdctl --endpoints=$ENDPOINTS get foo
etcdctl --endpoints=$ENDPOINTS --write-out="json" get foo
```

## see also
- [[consul]]
- [[zookeeper]]
