---
title: varnishstat
created: '2019-10-09T05:55:54.665Z'
modified: '2021-10-31T14:42:35.275Z'
---

# varnishstat

## usage

```sh
-1       # instead continuously updated display print to stdout
```

```sh
varnishstat -1 | awk '$2 > 0 {print $0}'
```

## see also

- [varnish-cache.org/docs/trunk/reference/varnishstat](https://varnish-cache.org/docs/trunk/reference/varnishstat.html)
- [book.varnish-software.com/4.0/chapters/Examining_Varnish_Server_s_Output](https://book.varnish-software.com/4.0/chapters/Examining_Varnish_Server_s_Output.html)
- [[awk]]
