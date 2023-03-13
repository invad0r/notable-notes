---
tags: [initsystem, linux]
title: sysvinit
created: '2019-08-21T06:49:32.889Z'
modified: '2019-08-22T07:23:20.639Z'
---

# sysvinit

```sh
/etc/init.d/docker status   # sysvinit - ubuntu 14.04
```

## service related commands

| comments          | SysVinit                | Systemd   |
|--                 |--                       |--         |
| start a service   | `service dummy start`   | `systemctl start dummy.service`   |
| stop a service    | `service dummy stop`    | `systemctl stop dummy.service`    |
| restart a service | `service dummy restart` | `systemctl restart dummy.service` |
| reload a service  | `service dummy reload`  | `systemctl reload dummy.service`  |
| service status    | `service dummy status`  | `systemctl status dummy.service`  |
| restart if running                      | `service dummy condrestart`   | `systemctl condrestart dummy.service` |
| enable service at startup               | `chkconfig dummy on`          | `systemctl enable dummy.service`      |
| disable service at startup              | `chkconfig dummy off`         | `systemctl disable dummy.service`     |
| check if service is enable at startup   | `chkconfig dummy`             | `systemctl is-enabled dummy.service`  |
| added service or modify configuration   | `chkconfig dummy --add`       | `systemctl daemon-reload`             |

## misc commands

| comments | SysVinit | Systemd |
|--|--|--|
| System halt       | `halt`            | `systemctl halt`      |
| System poweroff   | `poweroff`        | `systemctl poweroff`  |
| System reboot     | `reboot`          | `systemctl reboot`    |
| System suspend    | `pm-suspend`      | `systemctl suspend`   |
| System hibernate  | `pm-hibernate`    | `systemctl hibernate` |
| follow log file   | `tail -f /var/log/message or /var/log/syslog`   | `journalctl -f`   |

## see also

- [[upstart]]
- [SysVinit to Systemd Cheatsheet - Fedora Project Wiki](https://fedoraproject.org/wiki/SysVinit_to_Systemd_Cheatsheet)
