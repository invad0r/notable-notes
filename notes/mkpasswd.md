---
tags: [cryptography, linux]
title: mkpasswd
created: '2019-09-17T09:56:18.545Z'
modified: '2020-01-03T13:09:26.254Z'
---

# mkpasswd

> generate new password, optionally apply it to a user 

## install
`apt-get install whois`, `yum install expect`

## usage
```sh
mkpasswd --method=SHA-512   # opens prompt for password
```

## see also
- [etc-shadow-how-to-generate-6-s-encrypted-password](https://unix.stackexchange.com/questions/158400/etc-shadow-how-to-generate-6-s-encrypted-password)
- [[passwd]]
