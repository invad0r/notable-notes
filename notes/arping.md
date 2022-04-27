---
tags: [linux]
title: arping
created: '2019-12-26T19:30:34.765Z'
modified: '2022-04-06T11:36:24.621Z'
---

# arping

> send ARP requests to a neighbour host 

## install

`apt install arping`, `yum install arping`

## usage

```sh
arping                          # Send ARP request to a neighbour host

arping -I eth0 192.168.1.1      # Send ARP request to 192.168.1.1 via interface eth0

arping -D -I eth0 192.168.1.1   # Check for duplicate MAC addresses at 192.168.1.1 on eth0
```

## see also

- [[arp]]
- [[ping]]
