---
tags: [dns]
title: spf
created: '2022-01-26T08:24:32.923Z'
modified: '2023-03-22T10:29:40.362Z'
---

# spf

> Sender Policy Framework -  detect forging sender addresses during the delivery of email

##

```sh
v=VERSION     # defines the version of SPF used

ip4:IP        # specify the systems permitted to send messages for the given domain.
a
-all          # if the previous mechanisms did not match, the message should be rejected
```

## qualifiers

> Each mechanism can be combined with one of four qualifiers:

```sh
+         # for PASS result. This can be omitted; e.g., +mx is the same as mx.
?         # for NEUTRAL result interpreted like NONE (no policy).
~         # for SOFTFAIL, a debugging aid between NEUTRAL and FAIL. Typically, messages that return a SOFTFAIL are accepted but tagged.
-         # for FAIL, the mail should be rejected (see below).
```

```sh
"v=spf1 ip4:192.0.2.0/24 ip4:198.51.100.123 a -all"

TXT @ "v=spf1 a include:_spf.google.com ~all"
# TXT	     The DNS zone record type; SPF records are written as TXT records
# @	       In a DNS file, the "@" symbol is a placeholder used to represent "the current domain"
# v=spf1   Identifies the TXT record as an SPF record, utilizing SPF Version 1
# a	       Authorizes the host(s) identified in the domain's A record(s) to send e-mail include:	
#          Authorizes mail to be sent on behalf of the domain from google.com
# ~all	   Denotes that this list is all inclusive, and no other servers are allowed to send e-mail
```

## see also

- [wikipedia.org/wiki/Sender_Policy_Framework](https://en.wikipedia.org/wiki/Sender_Policy_Framework)
- [[dns]]
