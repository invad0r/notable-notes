---
tags: [dns, linux]
title: dig
created: '2019-07-30T06:19:49.037Z'
modified: '2019-09-24T04:30:43.937Z'
---

# dig

> `domain information groper`

## install
`apt install dnsutils`, `yum install bind-utils`, `apk add --no-cache bind-tools`

## specific nameserver
```sh
dig @server name type   # If no server argument is provided, dig consults /etc/resolv.conf
```

## options

```
+[no]all    Set or clear all display flags.

+[no]qr     Print [do not print] the query as it is sent. By default, the query is not printed.

+noall +answer +ttlid

dig +noall +answer +authority +additional na-cc.domain.net
```

## authorative query
```sh
dig +noall +answer ns {host.com,host.net,host.org}
```

## non authorative query
```sh
dig +noall +answer {host.com,host.net,host.org}
```

## see also
- [TTL when querying for any record with dig - Super User](https://superuser.com/a/873408/341187)

