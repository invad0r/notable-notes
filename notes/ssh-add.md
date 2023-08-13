---
tags: [crypto, ssh]
title: ssh-add
created: '2019-07-30T06:19:49.243Z'
modified: '2023-07-19T11:16:41.316Z'
---

# ssh-add

>  adds private key identities to the authentication agent

## option

```sh
-l             # list fingerprints of all identities currently represented by the agent
-L             # list public key parameters of all identities currently represented by the agent
-k             # add keys
```

## usage

```sh
ssh-add ~/.ssh/FILE

eval "$(ssh-agent -s)"        # add-ssh-key-to-agent
```

## see also

- [[ssh]]
- [[keychain]]
- [[bash eval]]
