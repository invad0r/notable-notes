---
tags: [osx]
title: osx scutil
created: '2019-07-30T06:19:49.202Z'
modified: '2019-08-19T14:10:04.908Z'
---

# osx scutil

```sh
scutil --dns
# or
cat /etc/resolv.conf
```


## list dns cache

```sh
grep nameserver <(scutil --dns)

tail -f /private/var/log/system.log

# then
sudo killall -INFO mDNSResponder

#.. mDNSResponder[100]: --------- DNS Servers(4) ----------
#.. mDNSResponder[100]: DNS Server . en0 192.168.30.30:53 0 Unscoped 30 320  v4 !v6 !cell DNSSECAware
..
```
[how-to-view-dns-cache-in-osx](https://stackoverflow.com/a/38882447/2087704)
