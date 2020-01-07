---
tags: [filesystem, linux]
title: fdisk
created: '2019-09-02T04:54:15.186Z'
modified: '2020-01-07T10:16:12.584Z'
---

# fdisk

> Partition table manipulator for Linux 

## usage
```sh
fdisk -l              # lists the partitions on your system.

fdisk -l /dev/sda     # only list partitions on the first disk


fdisk /dev/sda        # enter command mode
```

## see also
- [[mkfs]]
- [[filesystem]]
