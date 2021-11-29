---
tags: [network]
title: wireshark
created: '2020-01-27T14:43:12.327Z'
modified: '2021-10-31T14:51:12.828Z'
---

# wireshark

> starts gui network protocol analyzer that is used to interactively dump and analyze network traffic

## install

`brew install wireshark --with-qt`

## usage

```sh
-k                        # start capturing immediately
-i INTERFACE              # name or idx of interface
```

```sh
ssh USR@HOST "tcpdump -s0 -U -w - -n -i any 'dst 192.168.144.196||192.168.158.4 || port 53'" | wireshark -k -i -
```

## see also

- [[nmap]]
- [[ssh]]
- [[tcpdump]]
