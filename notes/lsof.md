---
tags: [linux]
title: lsof
created: '2019-07-30T06:19:49.166Z'
modified: '2020-09-04T08:26:19.227Z'
---

# lsof

> list open files

## install
`brew install lsof` `apt-get install lsof` `apk add lsof` `pacman -S lsof` `yum install lsof` `dnf install lsof`
## usage
```sh
# options
# -i :PORT
# -P              don't convert port-number to port-name
# -w              ignore warnings; "lsof: no pwd entry for UID 100"

lsof -Pi :PORT

lsof -i :80 | grep LISTEN          # lsof command find out what is using port 80

lsof -iTCP

lsof -iUDP

lsof -i4

lsof -i6
```

## see also
- [[bash ulimit]]
- [[pmap]]
- [[mount]]
- [[ss]]
- [[nmap]]
- [lsof-no-pwd-entry-for-uid](https://unix.stackexchange.com/a/193920/193945)
