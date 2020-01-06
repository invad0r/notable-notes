---
tags: [ssh]
title: ssh-keygen
created: '2019-07-30T06:19:49.245Z'
modified: '2020-01-06T08:03:26.948Z'
---

# ssh-keygen

> tool for creating new authentication key pairs for `ssh`

## usage

```sh
ssh-keygen           -t rsa -b 4096                  -C "john@example.net"    # generate ssh-key 4096-bit rsa

ssh-keygen -o -a 100 -t ed25519 -f ~/.ssh/id_ed25519 -C "john@example.net"    # ed25519

  -t type           # key-types: rs1, dsa, ecdsa, ed25519, rsa
  -b bits           # default: 2048bits
  -f .ssh/id_rsa    # key-file path
  -C "comment"      # provides comment e.g. email

  -o                # save private keys using the new OpenSSH format rather than the more compatible PEM format
  -a rounds         # When saving a new-format private key (i.e. an ed25519 key or when the -o flag is set)



# @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
# @    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
# @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
# IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
# Someone could be eavesdropping on you right now (man-in-the-middle attack)!
# `Warning: the ECDSA host key for '..' differs from the key for the IP address `
ssh-keygen -R 10.32.23.234    # Remove the cached key on local machine

ssh-keygen -R host

ssh-keygen -R [host]:1234     # when non standart port is used
```

## see also
- [[ssh-copy-id]]
- https://medium.com/risan/upgrade-your-ssh-key-to-ed25519-c6e8d60d3c54
- https://en.wikibooks.org/wiki/OpenSSH/Client_Configuration_Files
