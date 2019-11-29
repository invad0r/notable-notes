---
title: varnishstat
created: '2019-10-09T05:55:54.665Z'
modified: '2019-10-09T06:11:56.904Z'
---

# varnishstat

## usage
```sh
varnishstat -1|awk '$2 > 0 {print $0}'

    # -1 	  instead continuously updated display print to stdout
```
## see also
- https://varnish-cache.org/docs/trunk/reference/varnishstat.html
- https://book.varnish-software.com/4.0/chapters/Examining_Varnish_Server_s_Output.html
