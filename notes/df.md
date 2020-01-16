---
tags: [filesystem, linux]
title: df
created: '2019-07-30T06:19:49.036Z'
modified: '2020-01-14T04:51:30.846Z'
---

# df

> `disk free` reports the amount of available disk space being used by file systems.

## usage
```sh
df -h     # human readable

df -l     #  Only display information about locally-mounted filesystems.

df -T     #  Print filesystem type e.g. aufs, ext4 ... does not work for OSX !


df -h     # -h, --human-readable  - print sizes in powers of 1024 (e.g., 1023M)

df -H     # -H, --si              - print sizes in powers of 1000 (e.g., 1.1G)

df -T     # -T, --print-type      - print file system type

df -i     # free inode
```

## see also
- [[du]]
- [[ls]]
