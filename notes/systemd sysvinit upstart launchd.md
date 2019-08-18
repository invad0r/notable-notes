---
tags: [linux]
title: systemd sysvinit upstart launchd
created: '2019-07-30T06:19:49.250Z'
modified: '2019-08-18T14:13:16.853Z'
---

# systemd sysvinit upstart launchd

central responsibility of an init system is to bring up userspace

```sh
pstree          # see what is running on PID1

systemd-cgls    # fedora systemd cgroup tree
```

## service related commands

| comments | SysVinit | Systemd |
|--|--|--|
| start a service   | `service dummy start`   | `systemctl start dummy.service`   |
| stop a service    | `service dummy stop`    | `systemctl stop dummy.service`    |
| restart a service | `service dummy restart` | `systemctl restart dummy.service` |
| reload a service  | `service dummy reload`  | `systemctl reload dummy.service`  |
| service status    | `service dummy status`  | `systemctl status dummy.service`  |
| restart if running  | `service dummy condrestart`  | `systemctl condrestart dummy.service`  |
| enable service at startup  | `chkconfig dummy on`  | `systemctl enable dummy.service`  |
| disable service at startup  | `chkconfig dummy off`  | `systemctl disable dummy.service`  |
| check if service is enable at startup  | `chkconfig dummy`  | `systemctl is-enabled dummy.service`  |
| create new service file/modify configuration | `chkconfig dummy --add`  | `systemctl daemon-reload`  |

## misc commands
| comments | SysVinit | Systemd |
|--|--|--|
| System halt       | `halt`            | `systemctl halt`      |
| System poweroff   | `poweroff`        | `systemctl poweroff`  |
| System reboot     | `reboot`          | `systemctl reboot`    |
| System suspend    | `pm-suspend`      | `systemctl suspend`   |
| System hibernate  | `pm-hibernate`    | `systemctl hibernate` |
| follow log file   | `tail -f /var/log/message or /var/log/syslog`   | `journalctl -f`   |

## systemd commands

```sh
systemd-analyze         # get the boot process duration with the following
systemd-analyze time

systemd-analyze blame   # list of all running units, ordered by the time taken to initialize

systemctl list-units

systemctl --failed      # list failed units
```

[SysVinit to Systemd Cheatsheet - Fedora Project Wiki](https://fedoraproject.org/wiki/SysVinit_to_Systemd_Cheatsheet)

```sh
/etc/init.d/docker status   # sysvinit - ubuntu 14.04

initctl status ${SERVICE}   # upstart - ubuntu 14.04
```

- [TipsAndTricks](https://www.freedesktop.org/wiki/Software/systemd/TipsAndTricks/)
- [Why systemd?](http://0pointer.de/blog/projects/why.html)

## launchd
launchd - mac osx

---

### service - wrapper

can be a wrapper script for:
* `/etc/init.d`
* `initctl` (upstart)
* `systemd`


[command line - Difference between Systemctl and Service - Ask Ubuntu](https://askubuntu.com/a/903405)

[~usd-import-team/ubuntu/+source/init-system-helpers - [no description]](https://git.launchpad.net/~usd-import-team/ubuntu/+source/init-system-helpers/tree/script/service?h=ubuntu/xenial)

