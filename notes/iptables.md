---
tags: [network]
title: iptables
created: '2019-07-30T06:19:49.083Z'
modified: '2019-08-02T07:48:12.351Z'
---

# iptables

```sh
iptables -L     # --list current rules

iptables -S     # -list-rules -S [chain [rulenum]]
                # Print the rules in a chain or all chains
```

```sh
iptables-save


# example docker nat rule
-A POSTROUTING -s 10.32.254.0/24 ! -o docker0 -j MASQUERADE

# rule belongs to chain `-A POSTROUTING` which allows modifying routed packets.

# applies to packets coming from the subnet `-s 10.32.254.0/24` 
# that are not going to be sent via the interface `! -o docker0` 
# where the latter is Dockers default bridge interface and the former is its IPv4 subnet.

# instructs to jump to `-j MASQUERADE` which assigns the corresponding IP of the outgoing interface to matching packets.

```
