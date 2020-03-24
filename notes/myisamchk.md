---
tags: [database]
title: myisamchk
created: '2019-08-29T06:08:17.952Z'
modified: '2020-03-18T15:27:35.288Z'
---

# myisamchk

## usage
```sh
myisamchk /var/lib/mysql/Abtelefoniertool/bewo_namen.MYI >> /tmp/myisamchk_log.txt	# checks corrupt table

myisamchk -r /var/lib/mysql/Abtelefoniertool/bewo_namen.MYI					  # repairs corrupt table								
```

## see also
- [[mysql]]
- [How To Repair Corrupted MySQL Tables Using myisamchk](http://www.thegeekstuff.com/2008/09/how-to-repair-corrupted-mysql-tables-using-myisamchk/)
