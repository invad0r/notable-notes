---
tags: [linux]
title: ldapsearch
created: '2019-07-30T06:19:49.153Z'
modified: '2020-07-27T06:56:01.746Z'
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
# -d LEVEL      debbugging level - useful for debugging ldapmodify and ldapadd are
#               LEVELs: 1=Trace, 2=Packets, 4=Arguments, 32=Filters, 128=ACL

ldapsearch \
  -h HOST \
  -p 389 \
  -w "PASSWORD" \
  -D "CN=Service LDAP-User,CN=Users,DC=foo,DC=bar,DC=baz" \
  -b "CN=foo,DC=bar,DC=baz,DC=us" \
  -s sub \
  "(objectclass=*)"

LDAPTLS_REQCERT=never ldapsearch \      # don't verify certificate !
  -H ldaps://HOST:636 \
  -w "PASSWORD" \
  -D "CN=Service LDAP-User,CN=Users,DC=foo,DC=bar,DC=baz"\
  -b "CN=foo,DC=bar,DC=baz,DC=us" \
  -s sub \
  -Z \
  "(objectclass=*)"

# example queries
"(objectclass=*)"
"(&(objectclass=user)(samaccountname=user))"
"(&(objectclass=user)(sn=user))"
"(&(objectClass=group)(|(cn=GROUP)))"
"(&(memberof=cn=GROUP,ou=OU,dc=DC,dc=DC,dc=US))"
"(&(objectClass=group)(&(cn=GROUP)(cn=GROUP)))"
"(&(objectCategory=person)(|(objectClass=user)))"
```
## see also
- [ldapsearch (man pages section 1: User Commands)](https://docs.oracle.com/cd/E19455-01/806-0624/6j9vek58u/index.html)
