---
tags: [dns]
title: BIND
created: '2019-07-30T06:19:49.027Z'
modified: '2023-03-20T08:58:45.389Z'
---

# BIND

> `berkeley internet name domain` - implements the DNS protocols and a software distribution which contains all of the software necessary for `asking` and `answering` name service questions

### The BIND software distribution has three parts

1. domain name resolver
 resolver is a program that resolves questions about names by sending those questions to appropriate servers and responding appropriately to the servers
 stub resolver library
2. domain name authority server - authoritative DNS server answers requests from resolvers
3. tools - diagnostic and operational tools such as the `dig`

## install

```sh
yum install bind bind-utils
```

## usage

`BIND`’s process is known as [[named]]

```sh
/var/lib/named/slave/domain.net.zone
```

## see also

- [[dig]]
- [[named]]
- [[dnsmasq]]
- [[rndc]]
- [Domain name resolution - ArchWiki](https://wiki.archlinux.org/index.php/resolv.conf)
