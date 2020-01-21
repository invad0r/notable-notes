---
tags: [linux]
title: mount
created: '2019-07-30T06:19:49.179Z'
modified: '2020-01-20T19:52:23.559Z'
---

# mount

## usage

```sh
mount | column -t

# nfs4
mount -v -t nfs4 \
  -o nfsvers=4,rw,async \
  10.32.23.10:/nfs-server \
  /var/lib/nfs/data

# bind
# A bind mount is an alternate view of a directory tree.
mount --bind /some/where /else/where
mount -o bind /some/where /else/where
```


```sh
mount | mount | grep "^/dev" | awk '{print $1" " $5}'   # filesystem of partitions
/dev/sda2 ext4
/dev/sda1 vfat
/dev/sda2 ext4
```

## see also
- [[fstab]]
- [[findmnt]]
- [[docker volume]]
- [[cryptsetup]]
- [what-is-a-bind-mount - unix.stackexchange.com](https://unix.stackexchange.com/a/198591/193945)
