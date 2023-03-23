---
tags: [linux]
title: whois
created: '2021-12-23T09:09:20.217Z'
modified: '2023-03-22T10:35:10.686Z'
---

# whois

> utility to look up records in databases maintained by several `NICs` (=Network Information Centers)
> default first querying the `IANA` (=Internet Assigned Numbers Authority) whois serve

## env

```sh
WHOIS_SERVER      # primary default whois server   - if unset, whois uses RA_SERVER
RA_SERVER         # secondary default whois server - if unset, whois will use whois.iana.org
```

## usage

```sh
whois HOST
```

## see also

- [[dig]]
- [[host]]
- [[nslookup]]
