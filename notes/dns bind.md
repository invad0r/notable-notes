---
tags: [dns]
title: dns bind
created: '2019-07-30T06:19:49.027Z'
modified: '2019-09-24T04:30:20.997Z'
---

# dns bind 

> `berkeley internet name domain`

- BIND implements the DNS protocols
- BIND software distribution contains all of the software necessary for `asking` and `answering` name service questions.


## The BIND software distribution has three parts:

1. Domain Name Resolver
 resolver is a program that resolves questions about names by sending those questions to appropriate servers and responding appropriately to the servers
 stub resolver library


2. Domain Name Authority Server
 authoritative DNS server answers requests from resolvers

3. Tools
  diagnostic and operational tools such as the `dig`

```sh
/var/lib/named/slave/domain.net.zone
```

## see also
- [Domain name resolution - ArchWiki](https://wiki.archlinux.org/index.php/resolv.conf)
