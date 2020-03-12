---
tags: [php]
title: php
created: '2019-07-30T06:19:49.206Z'
modified: '2020-03-02T07:06:02.276Z'
---

# php

## usage
```sh
php -i 

php -a        # start php repl

php -r        # exec php code in oneline

# inline
php -r '
  echo gethostbyname("foo.bar.domain.net").PHP_EOL; 
  echo "---".PHP_EOL;
  foreach(dns_get_record("foo.bar.domain.net", DNS_A) as $i){ echo $i["ip"].PHP_EOL; };
'

# datatypes
# 8 primitives types:
#   4 scalar:	    boolean, integer, float, string
#   2 compound:   array, object
#   2 special:	  resource, NULL
# pseudo-types:   mixed, number, callback, array|oject, void)
```

## see also
- [[python]]
- [[scala]]
- [[irb]]
