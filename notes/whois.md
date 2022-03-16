---
title: whois
created: '2021-12-23T09:09:20.217Z'
modified: '2022-02-02T10:04:55.998Z'
---

# whois

> utility to look up records in databases maintained by several `NICs` (=Network Information Centers)
>   default first querying the `IANA` (=Internet Assigned Numbers Authority) whois server

## usage

```sh
WHOIS_SERVER      # primary default whois server   - if unset, whois uses RA_SERVER
RA_SERVER         # secondary default whois server - if unset, whois will use whois.iana.org
```

```sh
whois HOST
```

## see also

- [[dig]]
- [[host]]
- [[nslookup]]
