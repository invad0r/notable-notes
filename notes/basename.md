---
tags: [coreutils]
title: basename
created: '2019-10-04T07:16:41.100Z'
modified: '2020-10-06T07:07:46.368Z'
---

# basename

> return filename or directory portion of pathname

## usage
```sh
basename -s .log $(ls /var/log/*.log)   # get only filename stripped from extension
```

## see also
- [[bash pwd]]
- [[dirname]]
- [[realpath]]
