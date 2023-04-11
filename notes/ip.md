---
tags: [iproute, network]
title: ip
created: '2019-09-03T11:51:54.855Z'
modified: '2023-04-11T20:13:58.411Z'
---

# ip

> edits and displays the configuration of network interfaces, routing, and tunnels

## install

```SH
apt install iproute2
yum install iproute
```

## option

```sh
-s, -stats, -statistics       # Output more information. -s -s => more verbose
-f, -family                   # inet, inet6, bridge, ipx, dnet, link
-4                            # shortcut for -family inet.
-6                            # shortcut for -family inet6.
-B                            # shortcut for -family bridge.
-0                            # shortcut for -family link.
-o, -oneline                  # output each record on a single line, replacing line feeds with the '\' character
```

### objects

```sh
address                   # protocol (IP or IPv6) address on a device.
addrlabel                 # label configuration for protocol address selection.
l2tp                      # tunnel Ethernet over IP (L2TPv3).
link                      # network device.
maddress                  # multicast address.
monitor                   # watch for netlink messages.
mroute                    # multicast routing cache entry.
mrule                     # rule in multicast routing policy database.
neighbour                 # manage ARP or NDISC cache entries.
netns                     # manage network namespaces.
ntable                    # manage the neighbor cache's operation.
route                     # routing table entry.
rule                      # rule in routing policy database.
tcp_metrics, tcpmetrics   # manage TCP Metrics.
tunnel                    # tunnel over IP.
tuntap                    # manage TUN/TAP devices.
xfrm                      # manage IPSec policies.
```

## usage

```sh
ip [OPTS] OBJECT {CMD|HELP}

# show queries
addr                            # display IP Addresses and property information (abbreviation of address)

ip addr                         # Show information for all addresses
ip addr show en0                # show info to interface en0

ip -4 addr show eth0 | grep -oP "(?<=inet ).*(?=/)"

ip addr show dev em1            # display information only for device em1
ip -brief -color address show
ip -br -c a s

link                            # Manage and display the state of all network interfaces
ip link                         # Show information for all interfaces
ip link show dev em1            # display information only for device em1
ip -s link                      # display interface statistics

route                           # display and alter the routing table
ip route                        # List all of the route entries in the kernel
ip ro                           # show IP-pakets route via default bridge
ip route show cache table all

maddr                           # Manage and display multicast IP addresses
ip maddr                        # display multicast information for all devices
ip maddr show dev em1           # display multicast information for device em1

neigh                           # Show neighbour objects; also known as the ARP table for IPv4
ip neigh                        # display neighbour objects
ip neigh show                   # arp cache
ip neigh show dev em1           # Show the ARP cache for device em1


help                            # display a list of commands and arguments for each subcommand
ip help                         # display ip commands and arguments
ip addr help                    # display address commands and arguments
ip link help                    # display link commands and arguments
ip neigh help                   # display neighbour commands and arguments

# multicast addressing
maddr add                                 # add a static link-layer multicast address
ip maddr add 33:33:00:00:00:01 dev em1    # add mutlicast address 33:33:00:00:00:01 to em1
ip maddr del 33:33:00:00:00:01 dev em1    # delete multicast address: 33:33:00:00:00:01 from em1

# modifying address andlink properties
ip addr add 192.168.1.1/24 dev em1        # Add address 192.168.1.1 with netmask 24 to device em1
ip addr del 192.168.1.1/24 dev em1        # Remove address 192.168.1.1/24 from device em1

link set                                  # Alter the status of the interface
ip link set em1 up                        # Bring em1 online
ip link set em1 down                      # Bring em1 offline
ip link set em1 mtu 9000                  # Set the MTU on em1 to 9000
ip link set em1 promisc on                # Enable promiscuous mode for em1

# adjust and view routes
route add                                         # Add an entry to the routing table
ip route add default via 192.168.1.1 dev em1      # Add a default route (for all addresses) via the local gateway 192.168.1.1 that can be reached on device em1
ip route add 192.168.1.0/24 via 192.168.1.1       # Add a route to 192.168.1.0/24 via the gateway at 192.168.1.1
ip route add 192.168.1.0/24 dev em1               # Add a route to 192.168.1.0/24 that can be reached on device em1

route delete                                      # Delete a routing table entry
ip route delete 192.168.1.0/24 via 192.168.1.1    # Delete the route for 192.168.1.0/24 via the gateway at 192.168.1.1

route replace                                     # Replace, or add if not defined, a route
ip route replace 192.168.1.0/24 dev em1           # Replace the defined route for 192.168.1.0/24 to use device em1

route get                                         # display the route an address will take
ip route get 192.168.1.5                          # display the route taken for IP 192.168.1.5

# manage arp table
neigh add                                                 # Add an entry to the ARP Table
ip neigh add 192.168.1.1 lladdr 1:2:3:4:5:6 dev em1       # Add address 192.168.1.1 with MAC 1:2:3:4:5:6 to em1

neigh del                                                 # Invalidate an entry
ip neigh del 192.168.1.1 dev em1                          # Invalidate the entry for 192.168.1.1 on em1

neigh replace                                             # Replace, or adds if not defined, an entry to the ARP table
ip neigh replace 192.168.1.1 lladdr 1:2:3:4:5:6 dev em1   # Replace the entry for address 192.168.1.1 to use MAC 1:2:3:4:5:6 on em1
```

## see also

- [[netstat]]
- [[vagrant]]
- [[arp]]
- [[ipv4]]
- [[net-tools]]
- [[iproute]]
- [[net-tools vs iproute]]
- [[ethtool]]
- [[iptables]]
- [[firewall-cmd]]
- [computerhope.com/unix/ip.htm](https://www.computerhope.com/unix/ip.htm)
- [man7.org/../man8/ip.8.html](http://man7.org/linux/man-pages/man8/ip.8.html)
