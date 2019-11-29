---
tags: [ssh, systemd]
title: sshd
created: '2019-07-30T06:19:49.246Z'
modified: '2019-10-23T14:48:58.875Z'
---

# sshd

> `openssh` ssh daemon 

## usage
```sh
service sshd restart

systemctl status sshd.service

systemctl start sshd.service

systemctl reload sshd.service
```

## config
```sh
/etc/ssh/sshd_config

# disable password authentication
PermitEmptyPasswords    no
PasswordAuthentication  no
UsePAM                  no  # Pluggable Authentication Modules
```

## see also
- [SSH public key auth fails when UsePAM is set to "no" - Server Fault](http://serverfault.com/a/475882/200496)
- [How to Disable Password Authentication for SSH](http://support.hostgator.com/articles/specialized-help/technical/how-to-disable-password-authentication-for-ssh)
