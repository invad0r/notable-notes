---
tags: [filesystem]
title: xfs_info
created: '2020-01-07T07:48:24.148Z'
modified: '2020-01-07T10:12:10.190Z'
---

# xfs_info

> `xfs_info` is equivalent to invoking xfs_growfs with `-n` , no change to be made to the filesystem

## usage
```sh
xfs_info -V           # get version

xfs_info /dev/sda1    # XFS file system information
```
## see also
- [[xfs]]
- [[xfs_growfs]]
- [[xfs_repair]]
- [[findmnt]]
