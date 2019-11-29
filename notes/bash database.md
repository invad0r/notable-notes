---
tags: [bash]
title: bash database
created: '2019-07-30T06:19:48.995Z'
modified: '2019-08-29T12:17:20.976Z'
---

# bash database

### simplest database
```sh
# usage: source db.sh
# then call db_set or db_get from cli

db_set() { echo "$1,$2" >> database; }

db_get() { grep "^$1," database | sed -e "s/^$1,//" | tail -n 1; }
```
## see also
- [Log-structured storage - Julia Evans](https://jvns.ca/blog/2017/06/11/log-structured-storage/)
