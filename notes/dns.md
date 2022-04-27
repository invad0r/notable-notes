---
tags: [dns]
title: dns
created: '2019-07-30T06:19:49.040Z'
modified: '2022-04-19T09:00:47.606Z'
---

# dns

> domain name system

- port 53 UDP/TCP
- `RFC 882` -> `RFC 1034`
- `RFC 883` -> `RFC 1035`
- "forward lookup"
- DNS-DB: NameServer
- ZoneFile: SOA (=Start of Authority), NAS, A, AAAA, CNAME, MX, PTR, TXT


## namespace

## zone

## record

> administrative concept, defines a part of the DNS namespace

### A - `address`

> holds the IPv4 address of a domain

### AAAA - `address`

> contains the IPv6 address for a domain

### CNAME - `canonical name`

> forwards one domain/subdomain to another domain, does NOT provide an IP address

must point to a domain, never to an IP address !

### MX

> Directs mail to an email server

### TXT

> Lets an admin store text notes in the record. often used for email security

### NS - `name server`

> Stores the `name server` for a DNS entry

### SOA - `start of authority`

> Stores admin information about a domain

- zone files must always start with a SOA record

```sh
ns-2048.awsdns-64.net. hostmaster.example.com. 1 7200 900 1209600 86400
#    |                      |                  |   |   |     |       |
#    |                      |                  |   |   |     |   minimum ttl - value defines length of time recursive resolver should cache
#    |                      |                  |   |   |   time in seconds that secondary server will keep trying to complete a zone transfer
#    |                      |                  |   |  retry interval seconds, that secondary server waits before retrying a failed zone transfer
#    |                      |                  |  refresh time seconds
#    |                      |         serial number, can be incremented when a record is updated
#    |         email address of admin @ is replace with .
#   nameserver that created the SOA record
```

### SRV

> Specifies a port for specific services

### PTR

> Provides a domain name in reverse-lookups


## see also

- [[axfr]]
- [[spf]]
- [[dig]]
- [[nslookup]]
- [[dnsmasq]]
- [[aws]]
- [No domain defined in /etc/resolv.conf](https://unix.stackexchange.com/a/128096/193945)
- [cloudflare.com/learning/dns/dns-records/](https://www.cloudflare.com/learning/dns/dns-records/)
