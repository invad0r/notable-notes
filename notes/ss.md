---
tags: [linux, network]
title: ss
created: '2019-08-18T19:35:04.208Z'
modified: '2020-01-23T12:42:53.409Z'
---

# ss
> display `socket statistics`

## install
`yum install iproute`, `apt install iproute`, `bew install ss`

## usage
```sh
# -a     Show all sockets (listening and non-listening)
# -e     Show detailed socket information
# -o     Show timer information
# -n     dont try to resolve ip addresses
# -p     show PIDs using the socket
#
#  listening or connection         which protocols ?
#  default: connections            default: all
#  -l listening                      -t: TCP
#  -a both                           -u: UDP
#                                    -x: unix domain sockets

ss -tunapls       # tuna, please! 
```

## see also
- [[netstat]]
- [[socat]]
