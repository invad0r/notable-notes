---
tags: [container]
title: container
created: '2019-07-30T06:19:49.031Z'
modified: '2020-03-12T14:04:03.471Z'
---

# container

## what is a Container ?
- isolated process
- namespaces
- cgroups
- layered FS

> "bundling up dependecies so we can ship code in a repeatable and secure way" - definition


### namespaces
> Isolation - what can we see ? 
- pid
- mnt ("pivot_root"/ chroot)
- net
- UTS (=`Unix Time Shairing`: hostname, domainname)
- IPC (message queues)
- user


### cgroups
> resource sharing
- limit sets of `procs` and `taskids` enforce resource sharing
- `/sys/fs/cgroup`

## see also
- [[containerd]]
- [[docker]]
- [[cgroup]]
- [[linuxkit]]
- [[runc]]
