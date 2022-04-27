---
tags: [dns]
title: dnsmasq
created: '2020-08-05T09:18:05.574Z'
modified: '2022-04-19T08:31:48.411Z'
---

# dnsmasq

> lightweight dhcp- and caching dns-server

## install

`yum install dnsmasq`, `apt-get install dnsmasq`

## usage

```sh
/etc/init.d/dnsmasq restart

systemctl [start|enable|status] dnsmasq

/etc/dnsmasq.conf

dnsmasq --test    # check config syntax for errors
```

## see also

- [[dns]]
- [[dig]]
- [[BIND]]
- [[dhcp]]
- [wiki.archlinux.org/index.php/dnsmasq](https://wiki.archlinux.org/index.php/dnsmasq)
