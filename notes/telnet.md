---
tags: [network]
title: telnet
created: '2019-07-30T06:19:49.252Z'
modified: '2019-08-02T07:46:54.565Z'
---

# telnet

## test email

```sh
telnet smtp.mydomain.com 25

helo your_domain.com
mail from:<test@your_domain.com>
rcpt to:<to_email@your_domain.com>
data
From: test@your_domain.com
Subject: test mail from command line

this is test number 1
sent from linux box
.
```
https://stackoverflow.com/a/11988455


```sh
telnet github.com 80

Trying 192.30.253.113...
Connected to github.com.
Escape character is '^]'.
GET / HTTP/1.1
Host: github.com
Connection: close

HTTP/1.1 301 Moved Permanently
Content-length: 0
Location: https://github.com/
Connection: close

Connection closed by foreign host.
```
