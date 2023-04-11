---
tags: [dns, linux]
title: dig
created: '2019-07-30T06:19:49.037Z'
modified: '2023-03-20T08:59:52.633Z'
---

# dig

> `domain information groper`

## install

```
brew install bind 

apt-get install dnsutils
yum install bind-utils
apk add --no-cache bind-tools
```

## env

```sh
IDN_DISABLE       # turn off IDN support
```

## option

```sh
-h                # Print a usage summary
-v                # prints version number and exit
-4                # only IPv4 should be used
-6                # only IPv6 should be used
-b ADDR[PORT]     # sets the source IP address of the query. The address must be a valid address on one of the host's network interfaces, or "0.0.0.0" or "::"
-c CLASS          # sets the query class. default class is IN; other classes are HS for Hesiod records or CH for Chaosnet records
-f FILE           # sets batch mode, in which dig reads a list of lookup requests to process from the given file
-m                # enables memory usage debugging
-p port           # sends the query to a non-standard port on the server, instead of the default port 53. test name server configured to listen for queries on a non-standard port
-q name           # specifies the domain name to query. This is useful to distinguish the name from other arguments.
-r                # options from $HOME/.digrc should not be read
-t TYPE           # resource record type to query. default query type is A, unless -x
-t TYPEnn         # zone transfer can be requested by specifying a type of AXFR. When an incremental zone transfer (IXFR) is required, set the type to ixfr=N
-u                # print query times should be provided in microseconds instead of milliseconds
-x ADDR           # sets simplified reverse lookups, for mapping addresses to names. no need to provide the name, class, and type arguments as dig automatically 
                  # performs a lookup for a name like 94.2.0.192.in-addr.arpa and sets the query type and class to PTR and IN respectively
-k KEYFILE                    # signs queries using TSIG or SIG(0) using a key read from the given file. Key files can be generated using tsig-keygen
-y [HMAC:]KEYNAME:SECRET      # signs queries using TSIG with the given authentication key
                              #   KEYNAME - name of the key
                              #   SECRET  - base64-encoded shared secret
                              #   HMAC    - key algorithm; hmac-md5, hmac-sha1, hmac-sha224, hmac-sha256, hmac-sha384, or hmac-sha512
```

[[dns]]

## .digrc

```sh
cat <<EOF > $HOME/.digrc
+nostats +nocomments +nocmd +noquestion +recurse
EOF
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

## return codes

```sh
0      # DNS response received, including NXDOMAIN status
1      # usage error
8      # couldn't open batch file
9      # no reply from server
10     # internal error
```

## usage

```sh
dig +short example.com

dig @server name type   # use specific nameserver, ff no server argument is provided, dig consults /etc/resolv.conf

dig +noall +answer +authority +additional example.com

dig +noall +answer ns {example.com,example.net,example.org}      # authorative query

dig +noall +answer {example.com,example.net,example.org}         # non authorative query

dig @8.8.8.8 +trace github.com


dig SOA HOST     # SOA - `start of authority`
ns-2048.awsdns-64.net. hostmaster.example.com. 1 7200 900 1209600 86400
#    |                      |                  |   |   |     |       |
#    |                      |                  |   |   |     |   minimum ttl - value defines length of time recursive resolver should cache
#    |                      |                  |   |   |   time in seconds that secondary server will keep trying to complete a zone transfer
#    |                      |                  |   |  retry interval seconds, that secondary server waits before retrying a failed zone transfer
#    |                      |                  |  refresh time seconds
#    |                      |         serial number, can be incremented when a record is updated
#    |         email address of admin @ is replace with .
#   nameserver that created the SOA record
```

## axfr

> `asynchronous transfer full range` 

- protocol for `"zone transfers"` for replication of [[dns]] data accross multiple dns-servers
- mechanism used by the DNS system to transfer zone information for a primary DNS server to several secondary DNS servers
- client-initiated request
- edit information on primary DNS server then use AXFR from secondary DNS server to download the entire zone

```sh
dig +short ns zonetransfer.me
nsztm1.digi.ninja.
nsztm2.digi.ninja.

dig axfr zonetransfer.me @nsztm1.digi.ninja.    # initiate an AXFR request to get a copy of the zone from the primary server
```

[acunetix.com/blog/articles/dns-zone-transfers-axfr](https://www.acunetix.com/blog/articles/dns-zone-transfers-axfr/)

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
