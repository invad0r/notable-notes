---
tags: [linux]
title: arping
created: '2019-12-26T19:30:34.765Z'
modified: '2023-03-25T12:45:27.436Z'
---

# arping

> send arp requests to a neighbour host 

## install

```sh
apt install arping
yum install arping
```

## usage

```sh
arping                          # send arp request to a neighbour host

arping -I eth0 192.168.1.1      # send arp request to 192.168.1.1 via interface eth0

arping -D -I eth0 192.168.1.1   # check for duplicate MAC addresses at 192.168.1.1 on eth0
```

## see also

- [[arp]]
- [[ping]]
