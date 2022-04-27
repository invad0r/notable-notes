---
tags: [dns]
title: host
created: '2019-07-30T06:19:49.080Z'
modified: '2022-04-19T07:17:53.366Z'
---

# host

> lookup utility

## flags

```sh
-t          # is used to select the query type (CNAME, NS, SOA, SIG, KEY, AXFR,..)
```

## usage

```sh
host localhost              # reverse lookup

host -t ns twitter.com      # verify NS
```

## see also

- [[dns]]
- [[dig]]
- [[whois]]
- [[hostnamectl]]
- [[hostname]]
