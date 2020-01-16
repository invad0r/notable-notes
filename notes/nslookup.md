---
title: nslookup
created: '2020-01-16T07:23:01.811Z'
modified: '2020-01-16T07:29:49.681Z'
---

# nslookup
> for querying `DNS` to obtain domain names or IP addresses, mapping or for any other specific DNS Records

## install
`apt install net-tools`  

## usage
```sh
nslookup example.com

nslookup example.com ns1.nsexample.com      # check the using of a specific DNS Serve

nslookup -type=any example.com              # find all of the available DNS records of a domain

nslookup -type=ns example.com               # check the NS records of a domain

nslookup -type=soa example.com              # query the SOA record of a domain

nslookup -query=mx example.com              # find the MX records responsible for the email exchange


nslookup 10.32.23.139
```

## see also
- [[dig]]
- [[ifconfig]]
