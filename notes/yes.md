---
tags: [coreutils]
title: 'yes'
created: '2020-05-06T11:21:08.436Z'
modified: '2020-09-01T12:43:12.188Z'
---

# yes

> output a string repeatedly until killed

## usage

```sh
# --help    display this help and exit 
# --version output version information and exit

yes [STRING]...     # Repeatedly output a line with all specified STRING(s), or 'y'.

yes OPTION

yes | rm -r large_directory

yes | fsck /dev/foo

yes | keytool -import -trustcacerts -alias "ALIAS" -file "CERT.pem" -cacerts -storepass "PASS"
```

## see also

- [[openssl]]
- [[fsck]]
- [endler.dev/yes](https://endler.dev/2017/yes/)
