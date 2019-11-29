---
tags: [filesystem, linux]
title: filesystem
created: '2019-07-30T06:19:49.053Z'
modified: '2019-10-04T09:17:49.480Z'
---

# filesystem

```sh
cat /proc/filesystems
```

# blocksize
```sh
sudo blockdev --getbsz /dev/sda
4096	# blocksize of filesystem is 4kB
```

## see also
- [Differences between /bin, /sbin, /usr/bin, /usr/sbin, /usr/local/bin, /usr/local/sbin - Ask Ubuntu](http://askubuntu.com/a/308048/219213)
- [Why are there so many different ways to measure disk usage? - Unix & Linux Stack Exchange](http://unix.stackexchange.com/questions/120311/why-are-there-so-many-different-ways-to-measure-disk-usage)
- [[chmod]]
- [[ext]]
- [[lsofs]]
- [[sysfs]]
- [[procfs]]
- [[nfs]]
- [[shm]]
- [[mount]]
- [[linux fhs]]
- [[chattr]]
