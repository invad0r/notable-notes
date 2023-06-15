---
tags: [macos]
title: diskutil
created: '2019-07-30T06:19:49.184Z'
modified: '2023-05-30T08:57:03.259Z'
---

# diskutil

> modify, verify and repair local disks

## usage

```sh
diskutil list

diskutil unmount /dev/disk2

diskutil eject /dev/disk2

diskutil secureErase freespace 4 /Volumes/Macintosh\ HD
#   0     Single-pass zero-fill erase
#   1     Single-pass random-fill erase
#   2     US DoD 7-pass secure erase
#   3     Gutmann algorithm 35-pass secure erase
#   4     US DoE algorithm 3-pass secure erase
```

## see also

- [[dd]]
- [[hdiutil]]
