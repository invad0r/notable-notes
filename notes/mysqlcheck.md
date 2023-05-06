---
tags: [database]
title: mysqlcheck
created: '2019-08-18T14:36:02.403Z'
modified: '2023-04-30T11:31:51.308Z'
---

# mysqlcheck

> checks, repairs, optimizes and analyzes tables

## install

```sh
```

## option

```sh
--verbose     # option will give you more information about what mysqlcheck is doing.
```

## usage

```sh
mysqlcheck --print-defaults

mysqlcheck -c DATABASE -uroot -p              # check database for corrupt tables

mysqlcheck -r DATABASE TABLE -uroot -p				# repair table
```

## see also

- [[mysql]]
- [mariadb.com/kb/en/library/mysqlcheck](https://mariadb.com/kb/en/library/mysqlcheck/)
- [mysqlcheck - thegeekstuff.com](http://www.thegeekstuff.com/2011/12/mysqlcheck)

