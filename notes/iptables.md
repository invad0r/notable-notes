---
tags: [linux, network]
title: iptables
created: '2019-07-30T06:19:49.083Z'
modified: '2022-03-04T07:51:32.001Z'
---

# iptables

> administration tool for IPv4 packet filtering and NAT 

## basic iptables options

```sh
-A, --append chain            # Add one or more rules to the end of the selected chain
-C, --check chain             # Check for a rule matching the specifications in the selected chain
-D, --delete chain	          # Delete one or more rules from the selected chain
-F, --flush 	                # Delete all the rules one-by-one
-I, --insert chain            # Insert one or more rules into the selected chain as the given rule number
-L, --list 	                  # Display the rules in the selected chain
-n, --numeric 	              # Display the IP address or hostname and post number in numeric format
-N, --new-chain name 	        # Create a new user-defined chain
-v, --verbose 	              # Provide more information when used with the list option
-X, --delete-chain name 	    # Delete the user-defined chain

-p, --protocol 	              # The protocol, such as TCP, UDP, etc.
-s, --source 	                # Can be an address, network name, hostname, etc.
-d, --destination             # An address, hostname, network name, etc.
-j, --jump 	                  # Specifies the target of the rule; i.e. what to do if the packet matches.
-g, --goto chain 	            # Specifies that the processing will continue in a user-specified chain.
-i, --in-interface 	          # Names the interface from where packets are received.
-o, --out-interface 	        # Name of the interface by which a packet is being sent.
-f, --fragment 	              # The rule will only be applied to the second and subsequent fragments of fragmented packets.
-c, --set-counters 	          # Enables the admin to initialize the packet and byte counters of a rule.

--ctstate state               # Define the list of states for the rule to match on.
                              #   NEW         - connection has not yet been seen.
                              #   RELATED     - connection is new, but is related to another connection already permitted.
                              #   ESTABLISHED - connection is already established.
                              #   INVALID     - traffic couldn't be identified for some reason
--match, -m match        # 
```

## usage

```sh
iptables -F                   # flush/remove all rules

iptables --list               # list all active rules by specification
iptables -L          
iptables -L DOCKER-INGRESS    # list only DOCKER-INGRESS chain


iptables -S, -list-rules -S  # Print the rules in a chain or all chains

iptables -S TCP               # show all of the rule specifications in the TCP chain
iptables -S DOCKER

iptables -t nat -L POSTROUTING    # list chain:POSTROUTING in table:nat

iptables -S DOCKER-USER
```

## backup restore
```sh
iptables-save    > iptables_bckp

iptables-restore < iptables_bckp
```

## rules
```sh
iptables -I INPUT -s 198.51.100.0 -j DROP
  # -I    - insert will add it to the beginning of a chain and will be applied first 
  #         to indicate a specific placement in the chain, you may also use a number with the -I option.
  # -s    - source
  # -j    - jump, target of the rule and what action will be performed if the packet is a match


iptables -A POSTROUTING -s 10.32.254.0/24 ! -o docker0 -j MASQUERADE   # docker nat rule

  # append to chain POSTROUTING which allows modifying routed packets
  # applies to packets coming from the subnet `-s 10.32.254.0/24` 
  # that are not going to be sent via the interface `! -o docker0` 
  # where the latter is Dockers default bridge-interface and the former is its IPv4-subnet
  # instructs to jump to MASQUERADE which assigns the corresponding IP of the outgoing interface to matching packets.


iptables -A DOCKER -d 172.17.0.2/32 ! -i docker0 -o docker0 -p tcp -m tcp — dport 443 -j ACCEPT   # docker
```


## netfilter tables
> tables are made up of `built-in` chains and may also contain `user-defined` chains
> built-in tables will depend on the kernel configuration and the installed modules
```sh
iptables -vL -t nat
```

`Filter` - This is the default table. Its built-in chains are:
- `Input`: packets going to local sockets
- `Forward`: packets routed through the server
- `Output`: locally generated packets

`Nat` - When a packet creates a new connection, this table is used. Its built-in chains are:
- `Prerouting`: designating packets when they come in
- `Output`: locally generated packets before routing takes place
- `Postrouting`: altering packets on the way out

`Mangle` - Used for special altering of packets. Its chains are:
- `Prerouting`: incoming packets
- `Postrouting`: outgoing packets
- `Output`: locally generated packets that are being altered
- `Input`: packets coming directly into the server
- `Forward`: packets being routed through the server

`Raw` - Primarily used for configuring exemptions from connection tracking. The built-in chains are:
- `Prerouting`: packets that arrive by the network interface
- `Output`: processes that are locally generated

`Security` - Used for MAC rules. After the `filter` table, the security table is accessed next. The built-in chains are:
- `Input`: packets entering the server
- `Output`: locally generated packets
- `Forward`: packets passing through the server


## see also
- [[iptables-extensions]]
- [[firewall-cmd]]
- [[nat]]
- https://www.linode.com/docs/security/firewalls/control-network-traffic-with-iptables/
