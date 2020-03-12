---
tags: [dns]
title: host
created: '2019-07-30T06:19:49.080Z'
modified: '2020-03-11T07:23:52.103Z'
---

# host

>lookup utility

```sh
# options:
# -t    is used to select the query type (CNAME, NS, SOA, SIG, KEY, AXFR,..)

host localhost              # reverse lookup

host -t ns twitter.com      # verify NS
```

## see also
- [[dig]]
- [[hostnamectl]]
- [[hostname]]
