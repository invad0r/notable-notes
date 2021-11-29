---
tags: [network]
title: tshark
created: '2020-01-28T07:24:02.894Z'
modified: '2021-10-31T15:04:42.657Z'
---

# tshark

> cli to dump and analyze network traffic

## install

`brew install wireshark`

## usage

```sh 
-i, --interface CAPTURE_INTERFACE       # -
-f CAPTURE_FILTER                       # set capture filter expression, can occur multiple times
                                        #   if used before the first occurrence of the -i option, it sets the default capture filter expression
-2                                      # perform a two-pass analysis, which causes tshark to buffer output until the entire first pass is done
-r IN_FILE                              # read packet data from IN_FILE, can be any supported capture file format
-w OUT_FILE                             # write raw packet data to OUT_FILE or to the standard output if outfile is '-'
                                        #   -w provides raw packet data, not text
                                        #   if you want text output you need to redirect stdout (e.g. using '>'), don't use the -w option for this

-G REPORT_TYPE
--elastic-mapping-filter PROTOCOLS
```

```sh
tshark -D           # print list of interfaces and exit

tshark -i wlp61s0   # capture packets
```

## see also

- [[wireshark]]
- [[tcpdump]]
- [[namp]]
