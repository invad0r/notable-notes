---
tags: [ssh]
title: sshpass
created: '2019-07-30T06:19:49.247Z'
modified: '2020-01-24T14:48:20.445Z'
---

# sshpass

> provide the password for ssh based login

## usage
```sh
sshpass -p "PASS" ssh -o StrictHostKeyChecking=no USER@HOST

sshpass -p "PASS" ssh-o PreferredAuthentications=password -o PubkeyAuthentication=no -o StrictHostKeyChecking=no USER@HOST CMD

sshpass -p "PASS" ssh-copy-id USER@HOST -p PORT     # copy public key
```

## see also
- [[ssh]]
- [[ssh-copy-id]]
- [Login To SSH Server / Provide SSH Password Using A Shell Script - nixCraft](https://www.cyberciti.biz/faq/noninteractive-shell-script-ssh-password-provider/)
- [Using while loop to ssh to multiple servers - unix.stackexchange.com](https://unix.stackexchange.com/a/107801/193945)

