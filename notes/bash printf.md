---
tags: [bash/builtin]
title: bash printf
created: '2019-07-30T06:19:49.208Z'
modified: '2019-08-20T07:21:21.970Z'
---

# bash printf

```sh
printf '%x\n' 12  # print hex: C

printf "\33c"     # clear screen

printf "time: %s sec\n" $(expr $end - $start)


echo "$(printf '*%.s' {1..40})"     # draw line seperator

```

```sh
printf "%q\n" *   # show non visible characters in file name e.g.
```
