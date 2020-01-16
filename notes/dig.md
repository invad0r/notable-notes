---
tags: [dns, linux]
title: dig
created: '2019-07-30T06:19:49.037Z'
modified: '2020-01-16T07:29:21.700Z'
---

# dig
> `domain information groper`

## install
`apt install dnsutils`, `yum install bind-utils`, `apk add --no-cache bind-tools`

## usage
```sh
dig +short example.com

dig @server name type   # use specific nameserver, ff no server argument is provided, dig consults /etc/resolv.conf

# options:
#  +[no]all    Set or clear all display flags.
#  +[no]qr     Print [do not print] the query as it is sent. By default, the query is not printed.
#  +noall 
#  +answer
#  +ttlid

dig +noall +answer +authority +additional example.com

dig +noall +answer ns {example.com,example.net,example.org}      # authorative query

dig +noall +answer {example.com,example.net,example.org}         # non authorative query
```

## see also
- [[nslookup]]
- [TTL when querying for any record with dig - Super User](https://superuser.com/a/873408/341187)

