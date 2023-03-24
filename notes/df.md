---
tags: [coreutils, filesystem]
title: df
created: '2019-07-30T06:19:49.036Z'
modified: '2023-03-22T09:13:08.619Z'
---

# df

> `disk free` reports the amount of available disk space being used by file systems.

## flags

```sh
-h, --human-readable      # human readable, print sizes in powers of 1024 (e.g., 1023M)
-H, --si                  # print sizes in powers of 1000 (e.g., 1.1G)
-l                        # print only information about locally-mounted filesystems
-T, --print-type          # print filesystem type e.g. aufs, ext4 ... does not work on macos !
-i                        # free inodes
```

## usage

```sh
df -h
```

## see also

- [[du]]
- [[ls]]
