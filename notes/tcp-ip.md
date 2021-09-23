---
tags: [network]
title: tcp-ip
created: '2021-05-28T06:16:51.067Z'
modified: '2021-05-28T06:36:41.415Z'
---

# tcp-ip

> aka `internet protocol suite`, a conceptual model and set of communications protocols used in internet and networks
> foundational protocols in the suite are the [[tcp]] and [[ipv4]]
> concise version of the `osi`

## layers

```
Layer                     |
--                        |--
7 http                    | Process/Application Layer
4 tcp/udp                 | Host-to-Host/Transport Layer
3 ip-addr                 | Internet Layer
2 ethernet/wifi protocol  | Network Access/Link Layer
1 wire/waves
```

## osi
`Please Do Not Touch Steve's Pet Aligator` or `Please Do Not Throw Sausage Pizza Away`
```
Layer         |                         |
--            |--                       |--
Applicatoin   | End user Layer          | http, ftp, irc, ssh, dns
Presentation  | Syntax Layer            | ssl, ssh, imap, ftp, mpeg, jpeg
Session       | Sync and send to port   | api's, sockets, winsock
Transport     | End-to-end connection   | tcp, udp
Network       | Packets                 | ip, icmp, ipsec, igmp
Datalink      | Frames                  | ethernet, ppp, switch, bridge
Physical      | Physical Structure      | coax, fiber, wireless, hubs, repeaters
```



## see also
- [[telnet]]
- [[dns]]
- [[udp]]
- [[tcp]]
- [twitter.com/TechParida/status/1301064140002177024](https://twitter.com/TechParida/status/1301064140002177024)
- [trejrc0.blogspot.com/2006/09/osi-vs-7-layer-burrito.html](https://trejrc0.blogspot.com/2006/09/osi-vs-7-layer-burrito.html)
