---
tags: [linux]
title: iptables-extensions
created: '2019-10-30T09:17:47.113Z'
modified: '2019-12-30T07:56:42.674Z'
---

# iptables-extensions

> list of extensions in the standard iptables distribution

## usage
```sh
-m

-m tcp
-m conntrack
-m state --state RELATED,ESTABLISHED
-m conntrack --ctstate RELATED,ESTABLISHED
-m conntrack --ctstate INVALID

-m addrtype --dst-type
```

## see also
- [[iptables]]
