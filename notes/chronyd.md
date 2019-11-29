---
tags: [linux, systemd]
title: chronyd
created: '2019-10-26T17:55:51.285Z'
modified: '2019-11-15T06:41:42.539Z'
---

# chronyd

> `chrony` background daemon

## install
`yum install chrony`

## usage
```sh
/etc/chrony.conf    # config

systemctl start chronyd.service

systemctl enable chronyd.service
```

## see also
- [[chronyc]]
- [[timedatectl]]
