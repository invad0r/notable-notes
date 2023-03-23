---
tags: [cryptography, linux]
title: mkpasswd
created: '2019-09-17T09:56:18.545Z'
modified: '2023-03-22T08:55:23.002Z'
---

# mkpasswd

> generate new password, optionally apply it to a user 

## install

```sh
apt-get install whois
yum     install expect
```

## usage

```sh
mkpasswd --method=SHA-512   # opens prompt for password
```

## see also

- [etc-shadow-how-to-generate-6-s-encrypted-password](https://unix.stackexchange.com/questions/158400/etc-shadow-how-to-generate-6-s-encrypted-password)
- [[passwd]]
- [[xkcdpass]]
