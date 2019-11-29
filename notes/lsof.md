---
tags: [linux]
title: lsof
created: '2019-07-30T06:19:49.166Z'
modified: '2019-10-05T17:11:45.477Z'
---

# lsof

`list open files`

## open ports

```sh
-P  # don't convert port-number to port-name


lsof -Pi :PORT

lsof -iTCP
lsof -iUDP

lsof -i4
lsof -i6
```

### ignore warnings

```sh
lsof: no pwd entry for UID 100

lsof -w     # ignore warnings
```

## see also
- [[list open ports]]
- [[ls]]
- [lsof-no-pwd-entry-for-uid](https://unix.stackexchange.com/a/193920/193945)
