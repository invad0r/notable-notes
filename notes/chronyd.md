---
tags: [linux, systemd]
title: chronyd
created: '2019-10-26T17:55:51.285Z'
modified: '2023-03-23T08:45:48.486Z'
---

# chronyd

> `chrony` background daemon

## install

```sh
yum install chrony
```

## usage

```sh
/etc/chrony.conf    # config

systemctl start chronyd.service

systemctl enable chronyd.service
```

## see also

- [[chronyc]]
- [[timedatectl]]
