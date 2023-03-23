---
tags: [filesystem, linux]
title: sysfs
created: '2019-09-03T11:46:08.503Z'
modified: '2023-03-22T08:23:56.055Z'
---

# sysfs

> mounted on `/sys` as a way of exporting information from the kernel to various applications. "sysfs" generally contains 

## usage

```sh
/sys/block        # Contains known block devices
/sys/bus          # Contains all registered buses.

/sys/class              # Contains Devices
ls -l /sys/class/net    # show interfaces

/sys/device       # All devices known by the kernel organised by the bus that they connect to
/sys/firmware     # Contains firmware files for some devices

/sys/fs                                   # Contains files to control filesystems
/sys/fs/cgroup                            # umbrella for all cgroup hierarchies
cat /sys/fs/cgroup/memory/memory.stat

/sys/kernel       # Various kernel related files
/sys/module       # Loaded kernel modules. Each module is represented by a directory of the same name.
/sys/power        # Various files to handle power state of system
```

## see also

- [[container]]
- [[procfs]]
- [[mount]]
- [[arp]]
- [[ip]]
