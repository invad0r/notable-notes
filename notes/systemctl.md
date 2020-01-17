---
tags: [initsystem, linux, systemd]
title: systemctl
created: '2019-07-30T06:19:49.250Z'
modified: '2020-01-17T07:59:03.883Z'
---

# systemctl

> Query or send control commands to the systemd manager.

## usage

```sh
systemctl --failed            # list failed units

systemctl --type=service      # list current services

systemctl --state=running


systemctl list-units

systemctl list-units --all

systemctl list-units --all --state=inactive

systemctl list-units --type=service

systemctl list-unit-files --state=enabled

systemctl list-dependencies sshd.service


systemctl is-active application.service

systemctl is-enabled application.service

systemctl is-failed application.service


# Checking Unit Properties
systemctl show sshd.service             # get all properties

systemctl show unit.service --property=ActiveState


systemctl cat sshd.service              # cat unit-files fo service

systemctl edit --full sshd.service      # reload unit file after editing

systemctl daemon-reload


systemctl start unit.service

systemctl stop unit.service

systemctl restart unit.service


systemctl status unit.service

systemctl -l status service-name
    #   -l             # don't truncate entries with ellipses
    #   --no-pager     # can be added to avoid invoking a pager when the output is an interactive terminal. 

systemctl --output=json status docker-volume-netshare.service     
    # using output from `journalctl`
    # output: short, short-full, export, json, json-pretty, json-sse, json-seq, cat, with-unit
```

## see also
- [[journalctl]]
- [difference between service and systemctl? - serverfault.com](https://serverfault.com/questions/867322/what-is-the-difference-between-service-and-systemctl)
