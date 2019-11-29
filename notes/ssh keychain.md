---
tags: [ssh]
title: ssh keychain
created: '2019-07-30T06:19:49.148Z'
modified: '2019-11-15T06:54:27.903Z'
---

# ssh keychain

> `keychain` helps you to manage `ssh` and `gpg` keys in a convenient and secure manner. 
> It acts as a frontend to `ssh-agent` and `ssh-add`, but allows one long running ssh-agent process per system, rather than the norm of one ssh-agent per login session. 

## usage
```sh
eval $($keychain --eval id_rsa)       # avoid retyping passphrases 
```

## see also
- [[ssh]]
