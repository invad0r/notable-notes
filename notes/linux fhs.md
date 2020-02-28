---
tags: [linux]
title: linux fhs
created: '2019-09-02T05:06:01.427Z'
modified: '2020-02-24T12:22:05.700Z'
---

# linux fhs

> `Filesystem Hierarchy Standard` defines the directory structure and content in UNIX-like operating systems. It is based on the older standard `FSSTND` (Filesystem Standard).

```sh
/bin      # For binaries usable before the /usr partition is mounted.
          # This is used for trivial binaries used in the very early boot stage or
          # ones that you need to have available in booting single-user mode.
          # Think of binaries like cat, ls, etc.
/sbin     # Same, but for scripts with superuser (root) privileges required.
/usr/bin  # Same as first, but for general system-wide binaries.
/usr/sbin # Same as above, but for scripts with superuser (root) privileges required.
```

- all files and directories appear under the root directory `/`

| | |
|--  |-- |
| `/boot` | contains files related to the initial booting of the computer. |
| `/bin` | for binaries usable before the `/usr` partition is mounted. such as `ls`, `cp`, and `mount` |
| `/dev` | contains device files like hard disks or CD-ROMs. |
| `/sbin` | similar to /bin, but it contains programs that are normally run only by the system administrator. |
| `/etc` | contains configuration files. |
| `/home` | user’s home directory. |
| `/lib` | contains program libraries. |
| `/media` | mount point for removable media. |
| `/usr` | contains the majority of user utilities and applications. |
| `/var` | variable files such as logs. |
| `/tmp` | contains temporary files. |

## see also
- [[filesystem]]
- [[procfs]]
- [[sysfs]]
