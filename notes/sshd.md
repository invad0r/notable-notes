---
tags: [ssh, systemd]
title: sshd
created: '2019-07-30T06:19:49.246Z'
modified: '2020-07-14T12:22:32.684Z'
---

# sshd

> `openssh` ssh daemon 

## usage
```sh
systemctl [status|start|stop] sshd.service

service sshd [start|restart|stop]

sudo pkill -HUP sshd    # boot2docker restart sshd
```

## sshd_config
```sh
# sshd_config locations
/etc/ssh/sshd_config              # default
/usr/local/etc/ssh/sshd_config    # boot2docker sshd config

# disable password authentication
PermitEmptyPasswords    no
PasswordAuthentication  no
UsePAM                  no                # pluggable authentication modules


PermitRootLogin [yes|without-password]    # enable root login, not recommended !

PasswordAuthentication


UseDNS no     # defaults to `yes` if line doesn't exist, can delay login time
              # check if resolved hostname for connected client-ip maps back to same ip or not
```

## see also
- [[systemctl]]
- [[pkill]]
- [linux-tips.com/disabling-reverse-dns-lookups](https://linux-tips.com/t/disabling-reverse-dns-lookups-in-ssh/222)
- [SSH public key auth fails when UsePAM is set to "no"](http://serverfault.com/a/475882/200496)
- [How to Disable Password Authentication for SSH](http://support.hostgator.com/articles/specialized-help/technical/how-to-disable-password-authentication-for-ssh)
