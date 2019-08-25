---
tags: [filesystem, linux]
title: filesystem linux
created: '2019-07-30T06:19:49.053Z'
modified: '2019-08-23T11:10:57.519Z'
---

# filesystem linux

```sh
cat /proc/filesystems
```

## Filesystem Hierarchy Standard (FHS)
```sh
/bin      # For binaries usable before the /usr partition is mounted.
          # This is used for trivial binaries used in the very early boot stage or
          # ones that you need to have available in booting single-user mode.
          # Think of binaries like cat, ls, etc.
/sbin     # Same, but for scripts with superuser (root) privileges required.
/usr/bin  # Same as first, but for general system-wide binaries.
/usr/sbin # Same as above, but for scripts with superuser (root) privileges required.
```

# blocksize
```sh
sudo blockdev --getbsz /dev/sda
4096	# blocksize of filesystem is 4kB
```

# partition-fs
```sh
mount | mount | grep "^/dev" | awk '{print $1" " $5}'
/dev/sda2 ext4
/dev/sda1 vfat
/dev/sda2 ext4
```

# diskspace
```sh
sudo fdisk -l | grep Disk
```

## permissions
```sh
_ rwx rwx rwx [int] owner:group
^               ^
|               |
|               number of hardlinks
special permissions flag
    |
    _ = no special permissions
    d = directory
    l = file or dir as symlink
    s = setuid/set guid => run executable as owner with owner permissions
    t = sticky bit


chmod [u|g][+|-][r|w|x]
      |       |     ^
      |       |     |
      |       |     read write execute
      |       add or remove
      user or group
```

## see also
- [Differences between /bin, /sbin, /usr/bin, /usr/sbin, /usr/local/bin, /usr/local/sbin - Ask Ubuntu](http://askubuntu.com/a/308048/219213)
- [Why are there so many different ways to measure disk usage? - Unix & Linux Stack Exchange](http://unix.stackexchange.com/questions/120311/why-are-there-so-many-different-ways-to-measure-disk-usage)
- [[ext]]
- [[lsofs]]
- [[sysfs]]
- [[procfs]]
- [[nfs]]
- [[shm]]
