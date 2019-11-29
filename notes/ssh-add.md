---
tags: [ssh]
title: ssh-add
created: '2019-07-30T06:19:49.243Z'
modified: '2019-11-08T19:21:12.201Z'
---

# ssh-add

> `ssh-add` -- adds private key identities to the authentication agent

## usage
```sh
ssh-add ~/.ssh/PRIVATE_KEY

eval "$(ssh-agent -s)"            # add-ssh-key-to-agent

ssh-add -l        # Lists fingerprints of all identities currently represented by the agent.

ssh-add -L        # Lists public key parameters of all identities currently represented by the agent.
```

## see also
- [[bash eval]]
