---
tags: [linux]
title: apt-cache
created: '2019-11-28T11:57:30.886Z'
modified: '2020-04-21T08:30:28.253Z'
---

# apt-cache

> performs a variety of operations on apt's package cache - does not manipulate the state of the system, but provides operations to search and generate interesting output from the package metadata

## usage

```sh
apt-cache search REGEX    # full text search on available package lists; searches package names and descriptions         
                          # --full          output identical to show is produced for each matched package
                          # --names-only    long description is not searched, only the package name

apt-cache search lint

apt-cache search $i | grep -E "^$i\s"

apt-cache madison rabbitmq-server

apt-cache showpkg

apt-cache policy
```

## see also

- [[apt]]
