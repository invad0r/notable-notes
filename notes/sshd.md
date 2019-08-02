---
tags: [ssh]
title: sshd
created: '2019-07-30T06:19:49.246Z'
modified: '2019-08-02T07:37:52.099Z'
---

# sshd

### disable password authentication
```sh
sudo vim /etc/ssh/sshd_config

PermitEmptyPasswords no
PasswordAuthentication no
UsePAM no   # Pluggable Authentication Modules

sudo service sshd restart
```

[linux - SSH public key auth fails when UsePAM is set to "no" - Server Fault](http://serverfault.com/a/475882/200496)
[How to Disable Password Authentication for SSH « HostGator.com Support Portal](http://support.hostgator.com/articles/specialized-help/technical/how-to-disable-password-authentication-for-ssh)
