---
tags: [dns]
title: dns
created: '2019-07-30T06:19:49.040Z'
modified: '2022-01-26T08:32:31.576Z'
---

# dns

> domain name system

- port 53 UDP/TCP
- `RFC 882` -> `RFC 1034`
- `RFC 883` -> `RFC 1035`
- "forward lookup"
- DNS-DB: NameServer
- ZoneFile: SOA (=Start of Authority), NAS, A, AAAA, CNAME, MX, PTR, TXT

## resolve.conf config-directives

```sh
man resolv.conf

nameserver IP_ADDR   # Up to 3 name servers may be listed. 

domain LOCAL_DOMAIN_NAME 
  # resolving short host-names
  # e.g.:    domain example.com
  #          test => trys to resolve test.example.com

search SEARCH_LIST
  # search example.com example.net
  # test => will try test.example.com then test.example.net
```

## see also

- [[spf]]
- [No domain defined in /etc/resolv.conf](https://unix.stackexchange.com/a/128096/193945)
- [[dig]]
- [[nslookup]]
