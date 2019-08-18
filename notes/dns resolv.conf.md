---
tags: [dns, linux]
title: dns resolv.conf
created: '2019-07-30T06:19:49.039Z'
modified: '2019-08-02T07:40:09.944Z'
---

# dns resolv.conf

## resolve.conf config-directives

```sh
nameserver IP_ADDR   # Up to 3 name servers may be listed. 

domain LOCAL_DOMAIN_NAME 
  # resolving short host-names
  # e.g.:    domain example.com
  #          test => trys to resolve test.example.com

search SEARCH_LIST
  # search example.com example.net
  # test => will try test.example.com then test.example.net
```
[No domain defined in /etc/resolv.conf](https://unix.stackexchange.com/a/128096/193945)


```sh
sortlist

options

man resolv.conf
```
