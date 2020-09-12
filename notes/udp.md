---
tags: [network]
title: udp
created: '2019-07-30T06:19:49.256Z'
modified: '2020-09-03T07:03:30.191Z'
---

# udp

```
----FIRST BYTE--------- || ---SECOND BYTE-------

 0  1  2  3  4  5  6  7  0  1  2  3  4  5  6  7
+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+
|QR|   Opcode  |AA|TC|RD|RA|   Z    |   RCODE   |
+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+
```

```sequence
client->server: discovery
server->client: offer
client->server: request
server->client: acknowledge
```

## see also
- [[ipv4]]
- [[osi model]]
