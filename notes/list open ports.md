---
tags: [linux, network]
title: list open ports
created: '2019-07-30T06:19:49.165Z'
modified: '2019-11-28T08:14:03.184Z'
---

# list open ports

## usage
```sh
nmcli device show <interfacename> | grep IP4.DNS        # show dns nameserver
```

## scan network
```sh
nmap -sP 192.168.1.1/24

arp -a | awk '{ ahost=$1; aip=$2; gsub("()","",aip); print aip }';

arp -a | awk '{ gsub(/[()]/,""); print $1 " " $2}'
```

## see also
- [[lsof]]
- [[netstat]] tuna,please! 
- [[ss]]
- [[netstat]]
