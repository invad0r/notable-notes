---
tags: [linux]
title: filesystem linux
created: '2019-07-30T06:19:49.053Z'
modified: '2019-08-18T15:13:07.887Z'
---

# filesystem linux

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
[Differences between /bin, /sbin, /usr/bin, /usr/sbin, /usr/local/bin, /usr/local/sbin - Ask Ubuntu](http://askubuntu.com/a/308048/219213)
[Why are there so many different ways to measure disk usage? - Unix & Linux Stack Exchange](http://unix.stackexchange.com/questions/120311/why-are-there-so-many-different-ways-to-measure-disk-usage)


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

## problem: boot partition full
```sh
df -h

uname -r

cd /boot
du -sk * | sort -n

showmount
mountpoint

cat /etc/export
OR
showmount -e


dpkg --list 'linux-image*'

dpkg --configure -a
```

## types

* shm - shared memory a.k.a. tempfs
  * shm is shared data between processes not threads
  * can be used to set permissions on memory
* ext
  * ext2
  * ext3
  * ext4
* lsofs
* sysfs
* procfs
* nfs
* ntfs, vfat
* cifs = Common Internet File System; CIFS-Protcol successor to SMB-Protocol

```sh
cat /proc/filesystems

nodev   sysfs
nodev   rootfs
nodev   tmpfs
..
```
