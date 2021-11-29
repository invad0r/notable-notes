---
tags: [linux, net-tools, network]
title: arp
created: '2019-09-03T11:30:41.018Z'
modified: '2021-10-31T15:05:38.541Z'
---

# arp

> manipulates or displays the kernel's ipv4 network neighbour cache. It can add entries to the table, delete one, or display the current content.

## install

`apt install net-tools`

## usage

```sh
arp -a    # display (all) hosts in alternative (BSD) style

arp -a | awk '{ ahost=$1; aip=$2; gsub("()","",aip); print aip }'

arp -a | awk '{ gsub(/[()]/,""); print $1 " " $2}'        


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
- [omputerhope.com/unix/arp](https://www.computerhope.com/unix/arp.htm)
- [superuser.com/questions/1272010/where-is-the-arp-cache-on-linux](https://superuser.com/questions/1272010/where-is-the-arp-cache-on-linux)
