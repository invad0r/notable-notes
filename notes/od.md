---
tags: [linux]
title: od
created: '2019-09-04T06:17:03.101Z'
modified: '2020-01-03T08:30:57.897Z'
---

# od

> octal, decimal, hex, ASCII dump

## usage
```sh
od -b input.txt     # displays the contents of input in octal format

od -c input.txt     # displays the contents of input in character format.

od -An -c input.txt # displays the contents of input in character format but with no offset information


od -c -             # Accept input from command line. 
```

## see also
- [[ascii]]
- [[xxd]]
