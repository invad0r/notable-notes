---
tags: [dns, osx]
title: scutil
created: '2019-07-30T06:19:49.202Z'
modified: '2019-09-24T04:29:27.931Z'
---

# scutil

> Manage system configuration parameters on osx

## usage

```sh
scutil --get HostName
scutil --get LocalHostName
scutil --get ComputerName


scutil --dns
# or
cat /etc/resolv.conf
```


## list dns cache

```sh
grep nameserver <(scutil --dns)

tail -f /private/var/log/system.log

sudo killall -INFO mDNSResponder
```

## see also
- [how-to-view-dns-cache-in-osx](https://stackoverflow.com/a/38882447/2087704)
