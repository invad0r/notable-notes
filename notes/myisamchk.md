---
tags: [database]
title: myisamchk
created: '2019-08-29T06:08:17.952Z'
modified: '2019-12-30T07:33:15.384Z'
---

# myisamchk

## checks corrupt table
```sh
myisamchk /var/lib/mysql/Abtelefoniertool/bewo_namen.MYI >> /tmp/myisamchk_log.txt	
```

# repairs corrupt table
```sh
myisamchk -r /var/lib/mysql/Abtelefoniertool/bewo_namen.MYI													
```

## see also
- [[mysql]]
- [How To Repair Corrupted MySQL Tables Using myisamchk](http://www.thegeekstuff.com/2008/09/how-to-repair-corrupted-mysql-tables-using-myisamchk/)
