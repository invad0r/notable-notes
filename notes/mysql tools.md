---
tags: [database]
title: mysql tools
created: '2019-08-18T14:36:02.403Z'
modified: '2019-08-18T14:36:10.850Z'
---

# mysql tools

## mysqladmin
```sh
mysqladmin -u root -p -i 1 processlist
```

## mytop
```sh
mytop -h172.18.0.2 -uroot --prompt
```


## mysqlcheck
```sh
# check database for corrupt tables
mysqlcheck -c Abtelefoniertool -uroot -p							
  # Abtelefoniertool.besteller_info                    OK
  # Abtelefoniertool.bewo_namen
  # error    : Size of indexfile is: 1547264        Should be: 2399232
  # error    : Corrupt
  # Abtelefoniertool.config                            OK

# repair table
mysqlcheck -r Abtelefoniertool bewo_namen -uroot -p				
```
http://www.thegeekstuff.com/2011/12/mysqlcheck

## myisamchk
```sh
# checks corrupt table
myisamchk /var/lib/mysql/Abtelefoniertool/bewo_namen.MYI >> /tmp/myisamchk_log.txt	
# repairs corrupt table
myisamchk -r /var/lib/mysql/Abtelefoniertool/bewo_namen.MYI													
```
[How To Repair Corrupted MySQL Tables Using myisamchk](http://www.thegeekstuff.com/2008/09/how-to-repair-corrupted-mysql-tables-using-myisamchk/)
