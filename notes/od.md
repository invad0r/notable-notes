---
tags: [linux]
title: od
created: '2019-09-04T06:17:03.101Z'
modified: '2020-09-03T09:12:51.246Z'
---

# od

> octal, decimal, hex, ASCII dump

## usage
```sh
od -b input.txt     # displays the contents of input in octal format

od -c input.txt     # displays the contents of input in character format.

od -An -c input.txt # displays the contents of input in character format but with no offset information


od -c -             # Accept input from command line. 


# get decimal-set
echo '"' | tr -d "\n" | od -An -t uC
#          |            └────────────────  Use od (octal dump) to print:
#          |                                   -An    means Address none
#    remove "newline" char                     -t     select a type
#                                                  u  type is unsigned decimal.
#                                                  C  of size (one) char
```

## see also
- [[ascii]]
- [[xxd]]
- [[hexdump]]
