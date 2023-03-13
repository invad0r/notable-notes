---
tags: [linux]
title: grepcidr
created: '2020-09-02T17:09:18.874Z'
modified: '2022-11-29T08:07:04.572Z'
---

# grepcidr

> filter ipv4 and ipv6 addresses matching cidr patterns

## install

```sh
curl -LO http://www.pc-tools.net/files/unix/grepcidr-2.0.tar.gz 
tar xvzf grepcidr-2.0.tar.gz && cd grepcidr-2.0
make && make install
```

## flags

```sh
-V          #  show version
-c          #  show count of matching lines, instead lines
-i          #  inverse match, include lines without an IP, implies -v
-s          #  enforce strict alignment of CIDR mask; host portion must be all zero
-v          #  invert the sense of matching, output lines with IPs that don't match
-x          #  strict matching, only look at start of line
-e          #  specify individual IP or CIDR pattern(s) on command-line
-f          #  load individual IP or CIDR pattern(s) from file
```

## usage

```sh
grepcidr -f FILE LOG > abuse.log                # find cidr-anges from FILE that appear in LOG

grepcidr 2001:db8::/32 LOG_1 LOG_2              # Search for this IPv6 network inside two files

grepcidr 127.0.0.0/8 iplog                      # Searches for any localnet IP addresses inside the iplog file

grepcidr "192.168.0.1-192.168.10.13" iplog      # Searches for IPs matching indicated range in the iplog file

script | grepcidr -vf whitelist > blacklist     # Create a blacklist, with whitelisted networks removed (inverse)

grepcidr -f list1 list2                         # Cross-reference two lists, outputs IPs common to both lists
```

## see also

- [[grep]]
- [pc-tools.net/unix/grepcidr/](http://www.pc-tools.net/unix/grepcidr/)
- [manpages.ubuntu.com/manpages/xenial/man1/grepcidr](http://manpages.ubuntu.com/manpages/xenial/man1/grepcidr.1.html)
