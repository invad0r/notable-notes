---
tags: [linux, network]
title: ss
created: '2019-08-18T19:35:04.208Z'
modified: '2019-08-20T09:47:48.687Z'
---

# ss
> display `socket statistics`

```sh
ss -a   # Show all sockets (listening and non-listening)

ss -e   # Show detailed socket information

ss -o   # Show timer information

ss -n   # Do not resolve addresses

ss -p   # Show process using the socke
```

## tuna,please! [[list open ports]] 

```sh
ss -tunapls
  # -n - dont try to resolve ip addresses
  # -p show PIDs using the sockat
  # listening or connection         which protocols ?
  # default: connections            default: all
  # -l listening                      -t: TCP
  # -a both                           -u: UDP
  #                                   -x: unix domain sockets
```
