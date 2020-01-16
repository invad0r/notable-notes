---
tags: [linux, network]
title: netstat
created: '2019-08-28T22:19:06.348Z'
modified: '2020-01-16T07:57:23.069Z'
---

# netstat

## install
`yum install net-tools`, `apt install net-tools`, `zypper install net-tools`, `pacman -S netstat-nat`

## usage
```sh
netstat -c              # continuasly

netstat -s              # summary

netstat -st             # summary of tcp

netstat -tulpn          
    #  -l, [--listening|-l]   Show only listening sockets.  (These are omitted by default.)
    #  -p, [--program|-p]     Show the PID and name of the program to which each socket belongs
    #  -t, [--tcp|-t]
    #  -u, [--udp|-u]
    #  -n, [--numeric|-n]    Show numerical addresses instead of trying to determine symbolic host, port or user names

netstat -tunapl         # [--all|-a]
```

## see also
- [[ss]]
- [[ip]]
- [[net-tools vs iproute]]
- [[firewall-cmd]]
