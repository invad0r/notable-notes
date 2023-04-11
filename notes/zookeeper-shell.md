---
tags: [linux]
title: zookeeper-shell
created: '2019-09-23T09:47:31.660Z'
modified: '2023-04-11T11:09:58.933Z'
---

# zookeeper-shell

## usage

```sh
zookeeper-shell zookeeper-1:2181                # starts interactive shell

zookeeper-shell zookeeper-2:2181 ls /brokers/ids      # get a list of available brokers

echo stat | nc localhost 2181 | grep Mode             # determine which node is acting as a leader


# interactive mode
ls /brokers/ids               # list from path

ls / true                     # Watch can be set on any znode while using read operations like ls or get command. 
                              # Watch is set by setting the second argument of read operations as true:
```

## see also

- [[redis-cli]]
- [[consul]]
- [[etcdctl]]
- [[kafka]]
- [serverfault.com/get-zookeeper-cluster-status](https://serverfault.com/questions/801251/get-zookeeper-cluster-status)

