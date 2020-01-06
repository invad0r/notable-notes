---
tags: [linux]
title: xxd
created: '2019-09-04T06:14:01.648Z'
modified: '2020-01-03T08:39:45.594Z'
---

# xxd

>  make a hexdump or do the reverse

## usage

```sh
xxd docker-compose.yml    # hexdump file

xxd -plain                # output in postscript continuous hexdump style. Also known as plain hexdump style.

xxd -r <<<'0 4a'           # decimal
```

## see also
- [[url encoding]]
- [[ascii]]
- [[od]]
