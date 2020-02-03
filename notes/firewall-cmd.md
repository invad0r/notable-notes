---
tags: [linux]
title: firewall-cmd
created: '2019-08-23T13:34:33.074Z'
modified: '2020-01-30T12:20:41.283Z'
---

# firewall-cmd

> `firewalld` command line client

- `firewall-cmd` commands apply to runtime configuration by default 
- using the `--permanent` flag will establish a persistent configuration.

To add and activate a permanent rule, you can use one of two methods.

```sh
# Add the rule to both the permanent and runtime sets.
firewall-cmd --zone=public --add-service=http --permanent
firewall-cmd --zone=public --add-service=http

# Add the rule to the permanent set and reload FirewallD.
firewall-cmd --zone=public --add-service=http --permanent
firewall-cmd --reload
```

## usage

```sh
firewall-cmd --state

systemctl status firewalld


firewall-cmd --list-all               # print the whole firewalld configuration

firewall-cmd --list-services

firewall-cmd --runtime-to-permanent   # copy the running configuration to the permanent configuration
```

## zones
```sh
firewall-cmd --list-all-zones

firewall-cmd --get-default-zone

firewall-cmd --get-zones

firewall-cmd --get-active-zone

firewall-cmd --get-zone-of-interface=docker0
```

## services
```sh
firewall-cmd --set-default-zone=dmz
firewall-cmd --zone=dmz --add-interface=eth0

firewall-cmd --zone=dmz --add-service=http --permanent
firewall-cmd --zone=dmz --add-service=https --permanent

firewall-cmd --reload
```

## add port
```sh
firewall-cmd --zone=public --add-port=9002/tcp --permanent

firewall-cmd --reload
```

## rich rules

```sh
firewall-cmd --add-rich-rule

firewall-cmd --list-rich-rules

firewall-cmd --remove-rich-rule


# Allow all IPv4 traffic from host 192.0.2.0.
firewall-cmd --zone=public --add-rich-rule \
  'rule family="ipv4" source address=192.0.2.0 accept'

# Deny IPv4 traffic over TCP from host 192.0.2.0 to port 22.
firewall-cmd --zone=public --add-rich-rule \
  'rule family="ipv4" source address="192.0.2.0" port port=22 protocol=tcp reject'

# Allow IPv4 traffic over TCP from host 192.0.2.0 to port 80, and forward it locally to port 6532.
firewall-cmd --zone=public --add-rich-rule \
  'rule family=ipv4 source address=192.0.2.0 forward-port port=80 protocol=tcp to-port=6532'

# Forward all IPv4 traffic on port 80 to port 8080 on host 198.51.100.0 (masquerade should be active on the zone).
firewall-cmd --zone=public --add-rich-rule \
  'rule family=ipv4 forward-port port=80 protocol=tcp to-port=8080 to-addr=198.51.100.0'

# To list your current Rich Rules in the public zone:
firewall-cmd --zone=public --list-rich-rules



firewall-cmd --permanent --zone=public \
  --add-rich-rule='rule family=ipv4 source address=10.32.254.1/24 accept' \
  && firewall-cmd --reload

firewall-cmd --permanent --zone=public \
  --add-rich-rule='rule family=ipv4 source address=10.10.1.1/24 accept' \
  && firewall-cmd --reload
```

## iptables Direct InterfacePermalink
```sh
firewall-cmd --direct --get-all-chains

firewall-cmd --direct --get-all-rules
```

## see also
 - [[ip]]
 - [[firewalld]]
 - [[iptables]]
 - [[netstat]]
