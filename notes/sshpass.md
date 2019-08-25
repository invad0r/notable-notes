---
tags: [ssh]
title: sshpass
created: '2019-07-30T06:19:49.247Z'
modified: '2019-08-22T09:18:05.966Z'
---

# sshpass

> provide the password for ssh based login

```sh
sshpass -p 'secretpassword' ssh -o StrictHostKeyChecking=no username@server.example.com  

sshpass -p ${SSH_PASS} ssh \
  -n \
  -o PreferredAuthentications=password \
  -o PubkeyAuthentication=no \
  -o StrictHostKeyChecking=no \
  ${SSH_USER}@${host} $@
```

## see also
- [Login To SSH Server / Provide SSH Password Using A Shell Script - nixCraft](https://www.cyberciti.biz/faq/noninteractive-shell-script-ssh-password-provider/)
- [Using while loop to ssh to multiple servers - unix.stackexchange.com](https://unix.stackexchange.com/a/107801/193945)

