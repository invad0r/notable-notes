---
tags: [ssh, systemd]
title: sshd
created: '2019-07-30T06:19:49.246Z'
modified: '2020-01-03T13:17:26.534Z'
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
/etc/ssh/sshd_config

/usr/local/etc/ssh/sshd_config    # boot2docker sshd config
```
```sh
# disable password authentication
PermitEmptyPasswords    no
PasswordAuthentication  no
UsePAM                  no            # Pluggable Authentication Modules



PermitRootLogin yes                   # boot2docker allow root login for accessing docker-vol-paths
PermitRootLogin without-password


# Enable root login in /etc/ssh/sshd_config
sed -i 's/#PasswordAuthentication/PasswordAuthentication/g' /etc/ssh/sshd_config
sed -i 's/PermitRootLogin no/PermitRootLogin yes/g' /etc/ssh/sshd_config
systemctl restart sshd
```

## see also
- [SSH public key auth fails when UsePAM is set to "no"](http://serverfault.com/a/475882/200496)
- [How to Disable Password Authentication for SSH](http://support.hostgator.com/articles/specialized-help/technical/how-to-disable-password-authentication-for-ssh)
- [[systemctl]]
- [[pkill]]
