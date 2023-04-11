---
tags: [dns]
title: host
created: '2019-07-30T06:19:49.080Z'
modified: '2023-03-20T08:52:12.648Z'
---

# host

> lookup utility

## install

```sh
brew install bind
```

## option

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
