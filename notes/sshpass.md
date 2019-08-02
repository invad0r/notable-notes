---
tags: [ssh]
title: sshpass
created: '2019-07-30T06:19:49.247Z'
modified: '2019-08-02T07:54:25.567Z'
---

# sshpass

#### provide the password for ssh based login.
```sh
sshpass -p 'secretpassword' ssh -o StrictHostKeyChecking=no username@server.example.com  
```

```sh
sshpass -p ${SSH_PASS} ssh \
  -n \
  -o PreferredAuthentications=password \
  -o PubkeyAuthentication=no \
  -o StrictHostKeyChecking=no \
  ${SSH_USER}@${host} $@
```
[sshpass: Login To SSH Server / Provide SSH Password Using A Shell Script - nixCraft](https://www.cyberciti.biz/faq/noninteractive-shell-script-ssh-password-provider/)
[scripting - Using while loop to ssh to multiple servers - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/107801/193945)

