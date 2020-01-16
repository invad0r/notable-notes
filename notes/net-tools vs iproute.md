---
tags: [linux, network]
title: net-tools vs iproute
created: '2019-07-30T06:19:49.082Z'
modified: '2020-01-16T07:42:35.981Z'
---

# net-tools vs iproute

> comparing both toolsets

## usage
```sh
# net-tools                                                   ip-route commands
arp -a                                                        ip neigh
arp -v                                                        ip -s neigh
arp -s 192.168.1.1 1:2:3:4:5:6                                ip neigh add 192.168.1.1 lladdr 1:2:3:4:5:6 dev eth1
arp -i eth1 -d 192.168.1.1                                    ip neigh del 192.168.1.1 dev eth1

ifconfig -a                                                   ip addr
ifconfig eth0 down                                            ip link set eth0 down 
ifconfig eth0 up                                              ip link set eth0 up 
ifconfig eth0 192.168.1.1                                     ip addr add 192.168.1.1/24 dev eth0 
ifconfig eth0 netmask 255.255.255.0                           ip addr add 192.168.1.1/24 dev eth0 
ifconfig eth0 mtu 9000                                        ip link set eth0 mtu 9000 
ifconfig eth0:0 192.168.1.2                                   ip addr add 192.168.1.2/24 dev eth0 

netstat                                                       ss 
netstat -neopa                                                ss -neopa 
netstat -g                                                    ip maddr 

route                                                         ip route 
route add -net 192.168.1.0 netmask 255.255.255.0 dev eth0     ip route add 192.168.1.0/24 dev eth0 
route add default gw 192.168.1.1                              ip route add default via 192.168.1.1 
```

## see also
- [[ip]]
- [[arp]]
- [[netstat]]
- [rh_ip_command_cheatsheet_1214_jcs_print.pdf](https://access.redhat.com/sites/default/files/attachments/rh_ip_command_cheatsheet_1214_jcs_print.pdf)

