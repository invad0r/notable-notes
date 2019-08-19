---
tags: [linux]
title: systemd systemctl
created: '2019-07-30T06:19:49.250Z'
modified: '2019-08-19T09:11:57.284Z'
---

# systemd systemctl

[[systemd jounralctl]]

[What is the difference between service and systemctl? - Server Fault](https://serverfault.com/questions/867322/what-is-the-difference-between-service-and-systemctl)

```sh
systemctl list-unit-files --state=enabled

systemctl --type=service      # list current services

```


```sh
systemctl start foo.service

systemctl stop foo.service

systemctl restart foo.service
```

### status
```sh
systemctl status docker.service

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
[systemd/man/journalctl#-o](https://www.freedesktop.org/software/systemd/man/journalctl#-o)

### show property
```sh
systemctl show your.service     # get all properties

systemctl show docker-volume-netshare.service --property=ActiveState
```
