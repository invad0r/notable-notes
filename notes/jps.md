---
title: jps
created: '2020-08-27T08:49:45.295Z'
modified: '2020-08-27T09:33:17.174Z'
---

# jps

> jvm process status tool

## usage
```sh
jps                         # lists JVMs on localhost

jps -l remote.domain        # lists JVMs on remote host

jps -m remote.domain:2002   # lists JVMs on a remote host with a non-default port for the RMI registry
```

## see also
- [docs.oracle.com/javase/7/docs/.../jps.html](https://docs.oracle.com/javase/7/docs/technotes/tools/share/jps.html)
- [[jstat]]
- [[jstatd]]
- [[rmiregistry]]

