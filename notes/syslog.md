---
tags: [linux]
title: syslog
created: '2019-08-28T07:15:30.826Z'
modified: '2019-08-28T08:01:45.007Z'
---

# syslog

> log management

- `syslog` aka `sysklogd` default LM in common Linux 
- `rsyslog` "advanced" version of `sysklogd`
- `syslog-ng` "Next-Gen"
  - everything is object (source, destination, filter, and the very forwarding rule)


##
`/etc/rsyslog.conf`

## log files
| distribution         | global system       | logins and auth     |
|--                    |--                   |--                   |
| redhat/centos/fedora | `/var/log/messages` | `/var/log/secure`   |
| debian               | `/var/log/syslog`   | `/var/log/auth.log` |


## see also
- [[dmesg]]
- [[systemctl]]
- [[journalctl]]
- [difference-between-syslog-rsyslog-and-syslog-ng](https://serverfault.com/a/692329/200496)
- [rsyslog-journal-or-both](https://albertomolina.wordpress.com/2017/12/30/rsyslog-journal-or-both/)
