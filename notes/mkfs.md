---
tags: [filesystem, linux]
title: mkfs
created: '2019-09-02T05:00:34.964Z'
modified: '2023-03-22T09:14:18.112Z'
---

# mkfs

> `make filesystem` - build a Linux file system 

## usage

```sh
mkfs -t ext3 /dev/sdb1      # format the device at /dev/sdb1 with an ext3 file system. 
                            # Note that this will for sure delete all data you might have on that device!

mkfs.ext4 /dev/sdb1         # shortcut command
```

## see also

- [[fdisk]]
- [[filesystem]]
