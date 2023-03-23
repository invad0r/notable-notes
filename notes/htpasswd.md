---
tags: [cryptography]
title: htpasswd
created: '2020-01-10T07:57:18.726Z'
modified: '2023-03-22T08:54:46.166Z'
---

# htpasswd

> used to create and update the flat-files used to store usernames and password for basic authentication of HTTP users

## flag

```sh
-n     # display results on standard output rather than updating a file
-b     # use batch mode; i.e., get the password from the command line rather than prompting for it
-B     # use bcrypt encryption for passwords
```

## usage

```sh
htpasswd -nb -B admin <password> | cut -d ":" -f 2
```

## see also

- [httpd.apache.org/docs](https://httpd.apache.org/docs/2.4/programs/htpasswd.html)
- [[mkpasswd]]
- [[openssl passwd]]
- [[passwd]]
