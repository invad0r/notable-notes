---
tags: [ssh]
title: ssh-keygen
created: '2019-07-30T06:19:49.245Z'
modified: '2019-10-23T14:50:34.181Z'
---

# ssh-keygen

> tool for creating new authentication key pairs for `ssh`

## usage

```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"                           # generate ssh-key 4096-bit rsa

ssh-keygen -o -a 100 -t ed25519 -f ~/.ssh/id_ed25519 -C "john@example.com"      # ed25519

  -t type           # key-types: rs1, dsa, ecdsa, ed25519, rsa
  -b bits           # default: 2048bits
  -C "comment"      # provides comment e.g. email
  -f .ssh/id_rsa    # key-file path

  -o                # save private keys using the new OpenSSH format rather than the more compatible PEM format
  -a rounds         # When saving a new-format private key (i.e. an ed25519 key or when the -o flag is set)
```

### `Warning: the ECDSA host key for '..' differs from the key for the IP address `
```sh
ssh-keygen -R 10.32.23.234    # Remove the cached key on local machine
```

## see also
- [[ssh-copy-id]]
- https://medium.com/risan/upgrade-your-ssh-key-to-ed25519-c6e8d60d3c54
