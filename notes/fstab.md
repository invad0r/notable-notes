---
title: fstab
created: '2020-01-07T08:18:54.224Z'
modified: '2020-01-07T08:42:22.530Z'
---

# fstab

> can be used to define how disk partitions, various other block devices, or remote filesystems should be mounted into the filesystem

## usage
```sh
cat /etc/fstab

# If the line starts with UUID=xyz, this means it's a physical partition.
# If the line starst with /dev/sdaX, it also means it's a physical partition.
# The indicator for LVM would be something with /dev/mapper/xyz
```

## see also
- [[findmnt]]
- [[lvdisplay]]
- https://wiki.archlinux.org/index.php/fstab
