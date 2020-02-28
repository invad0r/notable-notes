---
tags: [linux]
title: lsof
created: '2019-07-30T06:19:49.166Z'
modified: '2020-02-20T09:44:26.144Z'
---

# lsof

> list open files

## install
`apt install lsof`

## usage
```sh
-P  # don't convert port-number to port-name

lsof -Pi :PORT

lsof -iTCP

lsof -iUDP

lsof -i4

lsof -i6

lsof -w     # ignore warnings; "lsof: no pwd entry for UID 100"
```

## see also
- [[ls]]
- [[ss]]
- [[nmap]]
- [lsof-no-pwd-entry-for-uid](https://unix.stackexchange.com/a/193920/193945)
