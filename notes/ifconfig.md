---
tags: [net-tools, network]
title: ifconfig
created: '2020-01-16T07:17:37.287Z'
modified: '2020-09-03T06:47:04.727Z'
---

# ifconfig
> configure a network interface 

## install
`apt install net-tools`

## usage
```sh
ifconfig eth1 up              # activate interface eth1

ifconfig wlan0 down           # disable an active network interface

ifconfig wlan0 69.72.169.1    # assign static ip
```

## see also
- [[nslookup]]
- [[ip]]    
