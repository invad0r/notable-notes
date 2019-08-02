---
tags: [osx]
title: osx - scutil
created: '2019-07-30T06:19:49.202Z'
modified: '2019-08-02T08:06:17.004Z'
---

# osx - scutil

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
#.. mDNSResponder[100]: DNS Server . en0 192.168.31.70:53 0 Unscoped 0 320  v4 !v6 !cell !DNSSECAware
#.. mDNSResponder[100]: DNS Server . en0 192.168.30.30:53 0 InterfaceScoped 30 328  v4 !v6 !cell !DNSSECAware
#.. mDNSResponder[100]: DNS Server . en0 192.168.31.70:53 0 InterfaceScoped 0 328  v4 !v6 !cell !DNSSECAware
#.. mDNSResponder[100]: v4answers 1
#.. mDNSResponder[100]: v6answers 1
#.. mDNSResponder[100]: Last DNS Trigger: 12385861 ms ago
#.. mDNSResponder[100]: --------- Mcast Resolvers ----------
#.. mDNSResponder[100]: Mcast Resolver local. timeout 5
#.. mDNSResponder[100]: Mcast Resolver 254.169.in-addr.arpa. timeout 5
#.. mDNSResponder[100]: Mcast Resolver 8.e.f.ip6.arpa. timeout 5
#.. mDNSResponder[100]: Mcast Resolver 9.e.f.ip6.arpa. timeout 5
#.. mDNSResponder[100]: Mcast Resolver a.e.f.ip6.arpa. timeout 5
#.. mDNSResponder[100]: Mcast Resolver b.e.f.ip6.arpa. timeout 5
#.. mDNSResponder[100]: Timenow 0xB2982B7C (-1298650244)
#.. mDNSResponder[100]: ----  END STATE LOG  ---- mDNSResponder mDNSResponder-625.60.2 (Jun  1 2016 21:57:20) OSXVers 15
```
[how-to-view-dns-cache-in-osx](https://stackoverflow.com/a/38882447/2087704)
