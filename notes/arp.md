---
tags: [linux, network]
title: arp
created: '2019-09-03T11:30:41.018Z'
modified: '2019-12-26T19:30:31.098Z'
---

# arp
> manipulates or displays the kernel's ipv4 network neighbour cache. It can add entries to the table, delete one, or display the current content.

## usage
```sh
arp -a    # display (all) hosts in alternative (BSD) style
arp -e    # display (all) hosts in default (Linux) style

arp -a 159.254.171.22


arp -i ens192   # display for interface


cat /proc/net/arp
```

## see also
- [[arping]]
- [[procfs]]
- [[ip]]
- [[net-tools vs iproute]]
- [unix/arp.htm](https://www.computerhope.com/unix/arp.htm)
- https://superuser.com/questions/1272010/where-is-the-arp-cache-on-linux
