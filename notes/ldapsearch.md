---
tags: [linux]
title: ldapsearch
created: '2019-07-30T06:19:49.153Z'
modified: '2020-01-03T14:09:21.179Z'
---

# ldapsearch

> `Lightweight Directory Access Protocol`
 
user authentication

This integration works with most LDAP-compliant directory servers, including:
- Microsoft Active Directory
- Apple Open Directory
- Open LDAP
- 389 Server

## install
`apt install ldap-utils`

## usage
```sh
ldapsearch \
  -D "CN=Service LDAP-User,CN=Users,DC=foo,DC=bar,DC=baz" \
  -w "password" \
  -p 389 \
  -h foo.bar.baz \
  -b "CN=users,DC=nade,DC=domain,DC=de" \
  -s sub \
  "(objectclass=*)"

"(&(objectclass=user)(samaccountname=user))"
"(&(objectclass=user)(sn=user))"

# -d debuglevel # Set the LDAP debugging level. Useful levels of debugging for ldapmodify and ldapadd are:
#    1       Trace
#    2       Packets
#    4       Arguments
#    32      Filters
#    128     Access control
```
## see also
- [ldapsearch (man pages section 1: User Commands)](https://docs.oracle.com/cd/E19455-01/806-0624/6j9vek58u/index.html)
