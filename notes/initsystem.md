---
tags: [initsystem, linux]
title: initsystem
created: '2019-07-30T06:19:49.250Z'
modified: '2019-08-22T07:17:27.278Z'
---

# initsystem

> central responsibility of an init system is to bring up userspace


## find out which initsystem is running
```sh
pstree          # see what is running on PID1

systemd-cgls    # fedora systemd cgroup tree
```

## see also
- [[systemd]]
- [[sysvinit]]
- [[upstart]]
- [[launchd]]
- [[service]]
