---
tags: [dns]
title: dns records
created: '2019-07-30T06:19:49.039Z'
modified: '2019-08-18T15:22:11.313Z'
---

# dns records

Nameserver
Zonefile

### Resource Records

###### SOA Resource Record
`Start of Authority`
```
Name            # Name of Zones
IN              # Zonenclass (IN for Internet)
SOA       
PRIMARY         # Primary Master for this zone 
Mail-Addr
Serialnumber    # JJJJMMTTVV; notic when zone was last updated
Refresh
Expire
TTL
```

```sh
dig +noall +answer +nottlid soa foo.bar
foo.bar. IN SOA ns8.foo.net. hostmaster.domain.net. 2017122100 28800 7200 604800 86400
```

### NS Resource Record
`Name Server`
| DOMAIN | TTL | Protokoll | Service | Server

Resource Record: A, AAAA, CNAME, MX, PTR, TXT
