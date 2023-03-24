---
tags: [Notebooks]
title: hyper text transfer protocol
created: '2022-02-02T12:54:22.385Z'
modified: '2023-03-23T10:16:13.340Z'
---

# hyper text transfer protocol

> hyper text transfer protocol

## tcp

- tcp is transport over ip
- established a "connection"
- 3-way handshake
- resend lost packages
- a reliable byte stream

## tls

- tls is done over tcp for `http/1` or `http/`
- transport layer security
- additional handshake +4
- privacy and security

## classic https stack

```
+------------------------------------------+
|                  https                   |
+------------------------------------------+
|                  tls                     |
+------------------------------------------+
|                  tcp                     |
+------------------------------------------+
|                  ip                      |
+------------------------------------------+
```

## `http/1.1`

- many parallel tcp connections
- better but ineffective tpc use
- http head-of-line-blocking

## `http/2`

- uses single connection per host
- many parallel streams
- tcp head-of-line-blocking (waiting for single packet)

## "ossification" 

- internet full of boxes -> routers, firewalls, LB -> boxes handle network data
- upgrade much slower than edges (browsers)
- casualties: 
  - `http/2` in clear text
  - tcp improvements like tfo (tcp-fast-open) -> os yes, boxes no
  - tcp/udp won't be replaced -> boxes only know tcp/udp
  - http brotli -> boxes only know gzip

## QUIC a transport protocol

- is a name not an acronym
- new transport protocol
- google deployed "`http/2` over UDP"-QUIC

## QUIC improvements

- tcp head-of-line-blocking
- faster handshakes
- earlier data
- connection-id, transition between network-ifaces
- more encryption, always

## build on top of udp

- tcp and udp remain "the ones"
- use udp instead of ip (move up one layer)
- "reliable transport protocol" - in user-space
- like reinventing tcp + tls in one layer

## udp isn't reliable, quic is

```
udp                   quic
---                   ---
connectionless        used udp like tcp uses ip
no resends            add connections
no flow control       reliability
no ordering           flow control
                      security
```

## quic has streams

- many logical flows within single connection
- similar to `http/2` but in the transport layer
- client or server initiated
- bidirectional or unidirectional
- independent streams

## application protocols over quic

- streams for free
- could be "any protocol"

## http - same but different

> http will stay the same

```
          Request
          - method + path    --- --- \
          - headers          --- --- /     server
client    - body
                              Response
           / --- ---         - response code
           \ --- ---         - headers
                             - body
```

- `http/2` - in [[ascii]] over tcp
- `http/2` - binary multiplexec over tcp
- `http/3` - binary multiplexec over quic


## https stack: old vs new

```
+--------+ +---------+       +-----------------+
| http/1 | | http/2 *|       |   http/3        |  * streams
+--------------------+       +-----------------+
|      tls           |       | quic (tls 1.3) *|
+--------------------+       +-----------------+
|      tcp           |       |   udp           |
+----------------------------------------------+
|                       ip                     |
+----------------------------------------------+
```

```
feature                   http/2      .   http/3
---                       ---         .   ---
transport                 tcp         .   quic
streams                   http/2      .   quic
clear-text version        yes         .   no
independent streams       no          .   yes
header compression        hpack       .   qpack
server push               yes         .   yes
early data                in theory   .   yes
0-rtt handhsake           no          .   yes
prioritization            messy       .   changes
```

## https:// is tcp ?

- `https://` urls are everywhere
- tcp and tls on tpc port `:443`

-> 

## see also

- [[ascii]]
- [[http]]
- [[12 factor app]]
- [[osi model]]
- [[tcp-ip model]]
- [[curl]]
- [daniel.haxx.se/blog/2020/02/02/http-3-for-everyone/](https://daniel.haxx.se/blog/2020/02/02/http-3-for-everyone/)
- [blog.cloudflare.com/even-faster-connection-establishment-with-quic-0-rtt-resumption](https://blog.cloudflare.com/even-faster-connection-establishment-with-quic-0-rtt-resumption/)
