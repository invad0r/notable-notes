---
tags: [ssh]
title: ssh-add
created: '2019-07-30T06:19:49.243Z'
modified: '2020-03-28T09:35:13.333Z'
---

# ssh-add

> `ssh-add` -- adds private key identities to the authentication agent

## usage
```sh
ssh-add ~/.ssh/PRIVATE_KEY

eval "$(ssh-agent -s)"        # add-ssh-key-to-agent

ssh-add -l                    # list fingerprints of all identities currently represented by the agent

ssh-add -L                    # list public key parameters of all identities currently represented by the agent

ssh-add -k                    # add keys
```

## see also
- [[ssh]]
- [[bash eval]]
