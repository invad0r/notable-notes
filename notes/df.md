---
tags: [filesystem, linux]
title: df
created: '2019-07-30T06:19:49.036Z'
modified: '2019-09-02T05:05:23.561Z'
---

# df

> `disk free` reports the amount of available disk space being used by file systems.


## options
```sh
df -h     # human readable

df -l     #  Only display information about locally-mounted filesystems.

df -T     #  Print filesystem type e.g. aufs, ext4 ... does not work for OSX !


df -h     # -h, --human-readable  - print sizes in powers of 1024 (e.g., 1023M)

df -H     # -H, --si              - print sizes in powers of 1000 (e.g., 1.1G)

df -T     # -T, --print-type      - print file system type
```

## see also
- 
