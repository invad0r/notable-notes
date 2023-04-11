---
tags: [linux]
title: od
created: '2019-09-04T06:17:03.101Z'
modified: '2022-11-25T11:28:24.762Z'
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
```

## see also

- [[ascii]]
- [[xxd]]
- [[hexdump]]
- [[rl]]
- [[tr]]
- [[bash echo]]
- [[bash printf]]
