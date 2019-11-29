---
title: zookeeper
created: '2019-09-23T09:47:31.660Z'
modified: '2019-10-02T08:10:21.042Z'
---

# zookeeper

## usage
```sh
echo stat | nc localhost 2181 | grep Mode     # determine which node is acting as a leader


zookeeper-shell.sh zookeeper-2:2181 ls /brokers/ids
```

## commands
```sh
ls /brokers/ids     # list from path

ls / true           # Watch can be set on any znode while using read operations like ls or get command. 
                    # Watch is set by setting the second argument of read operations as true:
```

## see also
- [[consul]]
- [[etcdctl]]
- [[kafka]]
- https://serverfault.com/questions/801251/get-zookeeper-cluster-status
