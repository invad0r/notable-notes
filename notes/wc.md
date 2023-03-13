---
title: wc
created: '2022-11-29T08:07:33.392Z'
modified: '2022-11-29T08:10:05.861Z'
---

# wc

> word count

## flags

```sh
-c      # number of bytes      in each input file is written to the STDOUT
-l      # number of lines      in each input file is written to the STDOUT
-m      # number of characters in each input file is written to the STDOUT
-w      # number of words      in each input file is written to the STDOUT
```

## usage

```sh
CMD | wc -l | xargs     # pipe to xargs to trim spaces

echo STRING | wc -c
```

## see also

- [[grep]]
- [[xargs]]
