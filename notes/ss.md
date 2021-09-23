---
tags: [iproute, network]
title: ss
created: '2019-08-18T19:35:04.208Z'
modified: '2021-06-06T08:32:41.634Z'
---

# ss

> display `socket statistics`

## install
`yum install iproute`, `apt install iproute`, `brew install ss`

## usage

```sh
-a      # Show all sockets (listening and non-listening)
-e      # Show detailed socket information
-o      # Show timer information
-n      # dont try to resolve ip addresses
-p      # show PIDs using the socket

-l      # listening                    
-a      # listening and connection                             
-t      # protocol: tcp
-u      # protocol: udp
-x      # protocol: unix domain sockets
```

```sh
ss -tunapls       # tuna, please! 
```

## see also
- [[netstat]]
- [[socat]]
- [[iproute]]
