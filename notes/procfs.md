---
tags: [filesystem, network]
title: procfs
created: '2019-09-03T11:42:10.908Z'
modified: '2023-03-22T07:57:21.733Z'
---

# procfs

> procfs or `/proc`, special linux filesystem used to present process information and kernel processes

## usage

```sh
cat /proc/meminfo   # memory info see also `free`

/proc/self/cgroup

/proc/self/mountinfo

/proc/filesystems     # available filesystems
```

## see also

- [[procps]]
- [[filesystem hierarchy standard]]
- [[filesystem]]
- [[sysfs]]
- [[free]]
- [[top]]
- [[container]]
