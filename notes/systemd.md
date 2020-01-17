---
tags: [initsystem, linux]
title: systemd
created: '2019-08-20T14:38:14.235Z'
modified: '2020-01-17T08:03:48.435Z'
---

# systemd

> systemd is a system and service manager for Linux, compatible with SysV and LSB init scripts
- Aggressive parallelization capabilities
- Uses `unix socket` and `D-Bus` activation for starting services
- Offers on-demand starting of daemons, keeps track of processes using Linux `cgroups`
- Supports snapshotting and restoring of the system state
- Maintains `mount` and `automount` points
- Implements an elaborate transactional dependency-based service control logic
- systemd manages `units`, which are representations of system resources and services `systemd unit`

## usage
```sh
systemd-analyze         # get the boot process duration with the following

systemd-analyze time

systemd-analyze blame   # list of all running units, ordered by the time taken to initialize
```

## see also
- [[systemctl]]
- [[unix socket]]
- [[d-bus]]
- [[cgroups]]
- [[systemd unit]]
- [understanding-and-administering-systemd](https://docs.fedoraproject.org/en-US/quick-docs/understanding-and-administering-systemd/#understanding-systemd)
- [Why systemd? - 0pointer.de](http://0pointer.de/blog/projects/why.html)
- [TipsAndTricks - freedesktop.org](https://www.freedesktop.org/wiki/Software/systemd/TipsAndTricks/)
