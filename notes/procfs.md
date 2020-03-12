---
tags: [filesystem, network]
title: procfs
created: '2019-09-03T11:42:10.908Z'
modified: '2020-03-03T12:56:48.221Z'
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
- [[filesystem]]
- [[sysfs]]
- [[free]]
- [[top]]
