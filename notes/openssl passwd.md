---
title: openssl passwd
created: '2019-10-11T06:34:34.744Z'
modified: '2019-10-11T06:36:59.173Z'
---

# openssl passwd

> generation of hashed passwords

## usage
```sh
openssl passwd MySecret      # generate hash: 8E4vqBR4UOYF.

openssl passwd -1 MySecret   # generate shadow-style-hash: $1$sXiKzkus$haDZ9JpVrRHBznY5OxB82.


# -crypt             standard Unix password algorithm (default)
```
## see also
- [[pass]]
- [[openssl rand]]
