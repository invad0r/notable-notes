---
tags: [ssh]
title: ssh-keygen
created: '2019-07-30T06:19:49.245Z'
modified: '2022-01-20T19:36:47.284Z'
---

# ssh-keygen

> tool for creating new authentication key pairs for [[ssh]]

## usage

```sh
-t TYPE             # key-types: rs1, dsa, ecdsa, ed25519, rsa
-b BITS             # default: 2048bits
-f .ssh/id_rsa      # key-file path
-C "COMMENT"        # provides comment e.g. email
-o                  # save private keys using the new OpenSSH format rather than the more compatible PEM format
-a ROUNDS           # When saving a new-format private key (i.e. an ed25519 key or when the -o flag is set)
-P PASSPHRASE       # passphrase, "" is the empty passphrase
```

```sh
ssh-keygen -t rsa -b 4096 -C "john@example.net"    # generate ssh-key 4096-bit rsa

ssh-keygen -t rsa -f .ssh/id_rsa  -q -P ""         # skip passphrase question

ssh-keygen -o -a 100 -t ed25519 -f ~/.ssh/id_ed25519 -C "john@example.net"    # ed25519


ssh-keygen -R 10.32.23.234      # Remove the cached key on local machine

ssh-keygen -R [host]:1234       # when non standart port is used
```

## see also

- [[ssh]] 
- [[ssh-keygen]]
- [[ssh-copy-id]]
- [medium.com/risan/upgrade-your-ssh-key-to-ed25519](https://medium.com/risan/upgrade-your-ssh-key-to-ed25519-c6e8d60d3c54)
- [en.wikibooks.org/wiki/OpenSSH/Client_Configuration_Files](https://en.wikibooks.org/wiki/OpenSSH/Client_Configuration_Files)
- [[vagrant]]
