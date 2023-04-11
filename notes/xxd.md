---
tags: [linux]
title: xxd
created: '2019-09-04T06:14:01.648Z'
modified: '2023-04-11T11:11:49.858Z'
---

# xxd

> make a hexdump or do the reverse

## usage

```sh
xxd docker-compose.yml    # hexdump file

xxd -plain                # output in postscript continuous hexdump style. Also known as plain hexdump style.

xxd -r <<<'0 4a'           # decimal
```

## see also

- [[bash echo]]
- [[ascii]]
- [[od]]
- [[hexdump]]
