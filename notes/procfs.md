---
tags: [filesystem, network]
title: procfs
created: '2019-09-03T11:42:10.908Z'
modified: '2021-03-19T10:43:29.622Z'
---

# procfs

> procfs or `/proc` is a special filesystem under Linux that is used to present process information and kernel processes

## usage
```sh
cat /proc/meminfo   # memory info see also `free`

/proc/self/cgroup

/proc/self/mountinfo

/proc/filesystems     # available filesystems
```

## see also
- [[filesystem hierarchy standard]]
- [[filesystem]]
- [[sysfs]]
- [[free]]
- [[top]]
