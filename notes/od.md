---
tags: [linux]
title: od
created: '2019-09-04T06:17:03.101Z'
modified: '2023-05-19T10:35:14.864Z'
---

# od

> `octal dump` - decimal, hex, [[ascii]] dump

## option

```sh
-b FILE     # displays contents of input in octal format
-c FILE     # displays contents of input in character format

-N 1        # read one byte from /dev/urandom
-An         # means Address none
-t T        # select a type
            #  d - signed decimal
            #  u - unsigned decimal
            #  C - of size (one) char
```

## usage

```sh
od -An -c FILE        # displays the contents of input in character format but with no offset information

od -c -               # accept input from STDIN

echo '"' | tr -d "\n" | od -An -t uC  # print/get decimal-set

od -An -td -N1 /dev/urandom      # dump random character

var="$(echo -n '☠' | od -An -tx1)"; printf '\\x%s' ${var^^}; echo

echo -n '"' | od -An -t uC   # get decimal-set
#                       └────────────────  Use od (octal dump) to print:
#                                              -An    means Address none
#                                              -t     select a type
#                                                  u  type is unsigned decimal.
#                                                  C  of size (one) char
```

## see also

- [[ascii]]
- [[xxd]]
- [[hexdump]]
- [[rl]]
- [[tr]]
- [[bash echo]]
- [[bash printf]]
- [[ascii]]
