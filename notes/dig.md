---
tags: [dns, linux]
title: dig
created: '2019-07-30T06:19:49.037Z'
modified: '2022-09-20T08:12:40.048Z'
---

# dig

> `domain information groper`

## install

```
apt-get install dnsutils
yum install bind-utils
apk add --no-cache bind-tools
```

## flags

```sh
-t TYPE       # any valid query type which is supported in BIND 9, default: A
```

## query options

```sh
+short        #
+[no]all      # set or clear all display flags.
+[no]qr       # print [don't print] the query as it is sent. By default, the query is not printed.
+noall        #
+answer       #
+ttlid        
```

## usage

```sh
dig +short example.com

dig @server name type   # use specific nameserver, ff no server argument is provided, dig consults /etc/resolv.conf

dig +noall +answer +authority +additional example.com

dig +noall +answer ns {example.com,example.net,example.org}      # authorative query

dig +noall +answer {example.com,example.net,example.org}         # non authorative query

dig @8.8.8.8 +trace github.com
```

## see also


- [[dns]]
- [[whois]]
- [[host]]
- [[nslookup]]
- [[rndc]]
- [[BIND]]
- [[dnstop]]
- [TTL when querying for any record with dig - Super User](https://superuser.com/a/873408/341187)
- [jvns.ca/blog/how-updating-dns-works/](https://jvns.ca/blog/how-updating-dns-works/)
