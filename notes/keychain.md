---
tags: [ssh]
title: keychain
created: '2019-07-30T06:19:49.148Z'
modified: '2023-07-19T11:16:16.391Z'
---

# keychain

> manages [[ssh]] and [[gpg]] keys in a convenient and secure manner, acts as a frontend to [[ssh-agent]] and [[ssh-add]], but allows one long running process per system, rather than one  per login session

## usage

```sh
eval $($keychain --eval id_rsa)       # avoid retyping passphrases 
```

## see also

- [[ssh]]
