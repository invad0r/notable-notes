---
tags: [linux, systemd]
title: firewalld
created: '2019-10-23T06:02:01.615Z'
modified: '2023-03-23T08:40:34.364Z'
---

# firewalld

> `firewalld` is frontend controller for `iptables` used to implement persistent network traffic rules

- `firewalld` uses `zones` and `services` instead of `chain` and `rules`.
- It manages rulesets dynamically, allowing updates without breaking existing sessions and connections.

## usage

```sh
systemctl start firewalld
systemctl enable firewalld

systemctl stop firewalld
systemctl disable firewalld

systemctl status firewalld
```

## config

- `firewalld` is configured with `xml` files
- `firewalld` uses two configuration sets:
  - `Runtime`: configuration changes are not retained on reboot or upon restarting FirewallD 
  - `Permanent`: changes are not applied to a running system.

```sh
/usr/lib/firewalld  # holds default configurations like default zones and common services. will be overwritten by each firewalld package update.

/etc/firewalld      # holds system configuration files. These files will overwrite a default configuration.
```

## see also

- [[firewall-cmd]]
- [[iptables]]
- https://firewalld.org/
- https://www.linode.com/docs/security/firewalls/introduction-to-firewalld-on-centos/
- [[systemd]]
- [[systemctl]]
