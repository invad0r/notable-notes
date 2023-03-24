---
tags: [linux]
title: fsck
created: '2020-05-06T13:18:59.979Z'
modified: '2023-03-23T10:14:58.774Z'
---

# fsck

> check and repair a linux filesystem 

## usage
```sh
umount /dev/sdb1
fsck /dev/sdb1


fsck -a /dev/sda1   # autorepair
fsck -y /dev/sda1   # yes everything

fsck -A             # check all filesystems
fsck -AR -y         # fix all except root-fs

fsck -M /dev/sdc1   # prevent checking mounted filesystem
```

## see also
- [[fdisk]]
- [[fstab]]
- [[mount]]
- [[yes]]
