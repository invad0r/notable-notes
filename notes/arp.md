---
tags: [linux, network]
title: arp
created: '2019-09-03T11:30:41.018Z'
modified: '2019-09-03T12:20:06.640Z'
---

# arp

> manipulates or displays the kernel's ipv4 network neighbour cache. It can add entries to the table, delete one, or display the current content.

```sh
arp -a    # display (all) hosts in alternative (BSD) style
arp -e    # display (all) hosts in default (Linux) style

arp -a 159.254.171.22


arp -i ens192   # display for interface
```

```sh
cat /proc/net/arp
```

## arping
```sh
arping                          # Send ARP request to a neighbour host
arping -I eth0 192.168.1.1      # Send ARP request to 192.168.1.1 via interface eth0
arping -D -I eth0 192.168.1.1   # Check for duplicate MAC addresses at 192.168.1.1 on eth0
```

## see also
- [[procfs]]
- [[ip]]
- [[net-tools vs iproute]]
- [unix/arp.htm](https://www.computerhope.com/unix/arp.htm)
- https://superuser.com/questions/1272010/where-is-the-arp-cache-on-linux
