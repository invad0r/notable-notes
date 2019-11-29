---
tags: [container/docker, linux]
title: unix socket
created: '2019-08-20T09:22:26.742Z'
modified: '2019-10-23T14:55:57.984Z'
---

# unix socket

> allows communication between two different processes `IPC`
> on either the same machine or different machines in client-server application frameworks

- Every UNIX systems Input/Output action is executed by writing or reading the descriptor file
- Descriptor file is an open file, which is associated with an integer
  - It can be a network connection, text file, terminal or something else. 
  - It looks and behaves much like a low-level file descriptor. 
  - This happens because the commands like read () and write () works with the same way they do with the files and pipes.



### socket
- combination of IP-Address and Port-Number
- 2 types:
  - stream - reliable two-way connected communication streams
  - datagram

## see also
- [[docker engine api]]
- [what-socket - linux.com](https://www.linux.com/news/what-socket)
- [[socat]]
