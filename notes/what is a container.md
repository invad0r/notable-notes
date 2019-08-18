---
tags: [container]
title: what is a container
created: '2019-07-30T06:19:49.031Z'
modified: '2019-08-02T07:44:48.466Z'
---

# what is a container

What is a Container ?
- isolated process
- namespaces
- cgroups
- layered FS

"bundling up dependecies so we can ship code in a repeatable and secure way" - definition


### namespaces

Isolation - what can we see ? 

- pid
- mnt ("pivot_root"/ chroot)
- net
- UTS (=`Unix Time Shairing`: hostname, domainname)
- IPC (message queues)
- user


### cgroups

resource sharing

limit sets of `procs` and `taskids` enforce resource sharing

`/sys/fs/cgroup`


## containerd

GPRC General Remote Procedure Call

CNCF Cloud Native Computing Foundation

"rich-client"-model


```
+---------------------------------------------------------+
|                  docker architecture                    |
+----------------+--------------+-----------------+-------+
|    docker      | containerd   | containerd-shim | runc  |
| engine/daemon  |              |                 |       |
+----------------+--------------+-----------------+-------+
```


```
           cli
            |
            v
   docker engine/daemon
            |
            v
       containerd
            |
    +----------------+
    |       |        |
    v       v        v
   shim    shim    shim

   runc    runc    runc

```
