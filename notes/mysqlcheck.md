---
tags: [database, mysql]
title: mysqlcheck
created: '2019-08-18T14:36:02.403Z'
modified: '2019-11-18T12:41:34.729Z'
---

# mysqlcheck

> checks, repairs, optimizes and analyzes tables

## usage
```sh
mysqlcheck --print-defaults

mysqlcheck -c DATABASE -uroot -p              # check database for corrupt tables

mysqlcheck -r DATABASE TABLE -uroot -p				# repair table


  # --verbose     option will give you more information about what mysqlcheck is doing.
```

## see also
- [[mysql]]
- https://mariadb.com/kb/en/library/mysqlcheck/
- [mysqlcheck - thegeekstuff.com](http://www.thegeekstuff.com/2011/12/mysqlcheck)

