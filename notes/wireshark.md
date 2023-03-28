---
tags: [network]
title: wireshark
created: '2020-01-27T14:43:12.327Z'
modified: '2023-03-25T12:48:59.536Z'
---

# wireshark

> starts gui network protocol analyzer that is used to interactively dump and analyze network traffic

## install

```sh
brew install wireshark --with-qt
```

## flag

```sh
-k                        # start capturing immediately
-i INTERFACE              # name or idx of interface
```

## usage

```sh
ssh USR@HOST "tcpdump -s0 -U -w - -n -i any 'dst 192.168.144.196||192.168.158.4 || port 53'" | wireshark -k -i -
```

## see also

- [[nmap]]
- [[ssh]]
- [[tcpdump]]
