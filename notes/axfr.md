---
title: axfr
created: '2022-04-19T08:32:12.828Z'
modified: '2022-04-19T08:45:55.971Z'
---

# axfr

> `asynchronous transfer full range` 

- protocol for `"zone transfers"` for replication of [[dns]] data accross multiple dns-servers
- mechanism used by the DNS system to transfer zone information for a primary DNS server to several secondary DNS servers
- client-initiated request
- edit information on primary DNS server then use AXFR from secondary DNS server to download the entire zone


## usage

```sh
dig +short ns zonetransfer.me
nsztm1.digi.ninja.
nsztm2.digi.ninja.

dig axfr zonetransfer.me @nsztm1.digi.ninja.    # initiate an AXFR request to get a copy of the zone from the primary server
```

## see also

 - [[dns]]
 - [[dig]]
 - [acunetix.com/blog/articles/dns-zone-transfers-axfr/](https://www.acunetix.com/blog/articles/dns-zone-transfers-axfr/)
