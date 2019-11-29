---
tags: [linux]
title: sort
created: '2019-07-30T06:19:49.240Z'
modified: '2019-10-23T14:55:05.952Z'
---

# sort

> sort or merge records (lines) of text and binary files

## usage
```sh
rpm -q kenerl   | sort -V                     # order by semantic version

du -d 1 -h      | sort -h                     # order by human readable output

sort -n -t . -k 1,1 -k 2,2 -k 3,3 -k 4,4      # # sort ip via gnu sort
```

## see also
- [Sort IP Addresses with GNU sort](https://www.madboa.com/geek/sort-addr/)
- [[du]]
