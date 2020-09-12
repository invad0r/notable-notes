---
tags: [network]
title: wireshark
created: '2020-01-27T14:43:12.327Z'
modified: '2020-09-02T17:42:33.039Z'
---

# wireshark

> starts gui network protocol analyzer that is used to interactively dump and analyze network traffic

## usage
```sh
# options:
# -k                        start capturing immediately
# -i <interface>            name or idx of interface


ssh USR@HOST "tcpdump -s0 -U -w - -n -i any 'dst 192.168.144.196||192.168.158.4 || port 53'" | wireshark -k -i -
```

## see also
- [[ssh]]
- [[tcpdump]]
