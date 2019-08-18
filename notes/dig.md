---
tags: [dns, linux]
title: dig
created: '2019-07-30T06:19:49.037Z'
modified: '2019-07-30T08:45:22.671Z'
---

# dig

`domain information groper`

### install
`apt install dnsutils`
`apk add --no-cache bind-tools`

### specific nameserver
```sh
dig @server name type   # If no server argument is provided, dig consults /etc/resolv.conf
```

### options

```
+[no]all    Set or clear all display flags.

+[no]qr     Print [do not print] the query as it is sent. By default, the query is not printed.

+noall +answer +ttlid

dig +noall +answer +authority +additional na-cc.domain.net
```

### authorative query
```sh
dig +noall +answer ns {ots.de,ots.ch,na.cc}

  # return 
  # ots.de.                 74019   IN      NS      ns8.colt.net.
  # ots.de.                 74019   IN      NS      ns1.de.colt.net.
  # ots.ch.                 86335   IN      NS      ns8.colt.net.
  # ots.ch.                 86335   IN      NS      ns1.de.colt.net.
  # na.cc.                  7835    IN      NS      ns8.colt.net.
  # na.cc.                  7835    IN      NS      ns1.de.colt.net.
```

### non authorative query
```sh
dig +noall +answer {ots.de,ots.ch,na.cc}
  # ots.de.                 73791   IN      A       46.137.127.165                                        
  # ots.ch.                 795     IN      A       46.137.127.165                                        
  # na.cc.                  7607    IN      A       46.137.127.165 
  
  # notice different ttl after seconr query 
  # ots.de.                 73641   IN      A       46.137.127.165
  # ots.ch.                 645     IN      A       46.137.127.165
  # na.cc.                  7457    IN      A       46.137.127.165
```
[dns - TTL when querying for any record with dig - Super User](https://superuser.com/a/873408/341187)

