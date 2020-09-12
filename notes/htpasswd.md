---
tags: [cryptography]
title: htpasswd
created: '2020-01-10T07:57:18.726Z'
modified: '2020-09-02T18:06:16.844Z'
---

# htpasswd

> used to create and update the flat-files used to store usernames and password for basic authentication of HTTP users

## usage
```sh
htpasswd -nb -B admin <password> | cut -d ":" -f 2

#  -n    Display the results on standard output rather than updating a file.
#  -b    Use batch mode; i.e., get the password from the command line rather than prompting for it.
#  -B    Use bcrypt encryption for passwords.
```

## see also
- [httpd.apache.org/docs](https://httpd.apache.org/docs/2.4/programs/htpasswd.html)
- [[mkpasswd]]
- [[openssl passwd]]
- [[passwd]]
