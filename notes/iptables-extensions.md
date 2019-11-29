---
title: iptables-extensions
created: '2019-10-30T09:17:47.113Z'
modified: '2019-10-30T09:41:43.521Z'
---

# iptables-extensions

>

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
