---
tags: [dns, macos]
title: scutil
created: '2019-07-30T06:19:49.202Z'
modified: '2022-02-02T10:11:07.858Z'
---

# scutil

> Manage system configuration parameters on macos

## usage

```sh
scutil --get HostName
scutil --get LocalHostName
scutil --get ComputerName


scutil --dns
# or
cat /etc/resolv.conf


grep nameserver <(scutil --dns)     # list dns cache

tail -f /private/var/log/system.log

sudo killall -INFO mDNSResponder
```

## see also

- [how-to-view-dns-cache-in-osx](https://stackoverflow.com/a/38882447/2087704)
