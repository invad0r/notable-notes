---
tags: [linux]
title: sort
created: '2019-07-30T06:19:49.240Z'
modified: '2019-08-21T06:10:54.298Z'
---

# sort

[[du]]

```sh
rpm -q kenerl   | sort -V     # order by semantic version
du -d 1 -h      | sort -h     # order by human readable output
```

## sort ip via gnu sort
```sh
sort -n -t . -k 1,1 -k 2,2 -k 3,3 -k 4,4
```
[Sort IP Addresses with GNU sort](https://www.madboa.com/geek/sort-addr/)
