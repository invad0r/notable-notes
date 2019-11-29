---
tags: [ssh]
title: ssh-copy-id
created: '2019-07-30T06:19:49.244Z'
modified: '2019-10-23T14:51:19.414Z'
---

# ssh-copy-id

> installs an `ssh` key on a server as an authorized key

## usage
```sh
ssh-copy-id user@host       # adds your ssh key to host

ssh-copy-id -i .ssh/foo@bar.pub user@server
```

## see also
- [[ssh]]
- [[ssh-keygen]]
