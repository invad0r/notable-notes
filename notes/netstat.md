---
tags: [linux, network]
title: netstat
created: '2019-08-28T22:19:06.348Z'
modified: '2019-11-15T06:56:00.118Z'
---

# netstat

## usage
```sh
netstat -c              # continuasly

netstat -s              # summary
netstat -st             # summary of tcp

netstat -lptu           # -l, [--listening|-l] Show only listening sockets.  (These are omitted by default.)
                        # -p, [--program|-p] Show the PID and name of the program to which each socket belongs
                        # -t, [--tcp|-t]
                        # -u, [--udp|-u]

netstat -lptuna         # [--all|-a]

netstat -lptun          # -n, [--numeric|-n] Show numerical addresses instead of trying to determine symbolic host, port or user names
```

## see also
- [[ss]]
- [[list open ports]]
- [[net-tools vs iproute]]
