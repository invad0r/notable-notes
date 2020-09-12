---
title: varnishstat
created: '2019-10-09T05:55:54.665Z'
modified: '2020-09-02T17:52:52.681Z'
---

# varnishstat

## usage
```sh
varnishstat -1 | awk '$2 > 0 {print $0}'

    # -1 	  instead continuously updated display print to stdout
```
## see also
- [varnish-cache.org/docs/trunk/reference/varnishstat](https://varnish-cache.org/docs/trunk/reference/varnishstat.html)
- [book.varnish-software.com/4.0/chapters/Examining_Varnish_Server_s_Output](https://book.varnish-software.com/4.0/chapters/Examining_Varnish_Server_s_Output.html)
- [[awk]]
