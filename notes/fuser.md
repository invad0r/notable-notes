---
tags: [linux]
title: fuser
created: '2020-03-09T10:22:00.327Z'
modified: '2020-09-02T17:52:01.714Z'
---

# fuser
> fuser - identify processes using files or sockets 

## usage
```sh
fuser /mnt/data           # find processes using a filesystem

fuser -k /mnt/data        # kill all processes using a filesystem
fuser -k -9 /mnt/data
```
## see also
- [[mount]]
- [[lsof]]
- [force-linux-unmount-filesystem-reporting-device-busy/](https://www.systutorials.com/force-linux-unmount-filesystem-reporting-device-busy/)
