---
tags: [initsystem, linux]
title: systemd systemctl
created: '2019-07-30T06:19:49.250Z'
modified: '2019-08-22T07:22:21.287Z'
---

# systemd systemctl

> Query or send control commands to the systemd manager.

```sh
systemctl --failed      # list failed units

systemctl --type=service      # list current services


systemctl list-units

systemctl list-units --all

systemctl list-units --all --state=inactive

systemctl list-units --type=service

systemctl list-unit-files --state=enabled

systemctl list-dependencies sshd.service


systemctl is-active application.service

systemctl is-enabled application.service

systemctl is-failed application.service
```

## Checking Unit Properties
```sh
systemctl show sshd.service
```

```sh
systemctl start unit.service

systemctl stop unit.service

systemctl restart unit.service
```

### status
```sh
systemctl status unit.service

systemctl -l status service-name

# -l             # don't truncate entries with ellipses
# --no-pager     # can be added to avoid invoking a pager when the output is an interactive terminal. 
```

#### using output from `journalctl`

```sh
systemctl --output=json status docker-volume-netshare.service

    # short
    # short-full
    # export
    # json
    # json-pretty
    # json-sse
    # json-seq
    # cat
    # with-unit
```

### show property
```sh
systemctl show unit.service     # get all properties

systemctl show unit.service --property=ActiveState
```

## see also
- [[systemd jounralctl]]
- [What is the difference between service and systemctl? - Server Fault](https://serverfault.com/questions/867322/what-is-the-difference-between-service-and-systemctl)
