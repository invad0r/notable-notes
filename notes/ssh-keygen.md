---
tags: [ssh]
title: ssh-keygen
created: '2019-07-30T06:19:49.245Z'
modified: '2019-08-02T07:37:52.098Z'
---

# ssh-keygen
```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"     # generate-ssh-key

  -t  #  type [rs1, dsa, ecdsa, ed25519, rsa]
  -b  #  bits default 2048bits
  -C  #  comment provides comment
  -f <$HOME/.ssh/id_rsa>

```

### Warning: the ECDSA host key for '..' differs from the key for the IP address 
```sh
ssh-keygen -R 10.32.23.234    # Remove the cached key on local machine
```
