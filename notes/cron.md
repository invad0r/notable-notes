---
tags: [linux]
title: cron
created: '2019-07-30T06:19:49.031Z'
modified: '2019-07-30T18:51:10.791Z'
---

# cron

```sh
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7)  OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  *  USER command to be executed
```

```sh
# find out which user has a crontab
for user in $(cut -f1 -d: /etc/passwd); do \
  echo $user; \
  crontab -u $user -l;   
done

cat /var/spool/cron/crontabs/root      # location of cron files for individual users


crontab -l | tee >(head -n1) | grep "^[^#;]"      # show only active jobs
```
[cron - Location of the crontab file - Unix & Linux Stack Exchange](http://unix.stackexchange.com/a/196010)



## debugging cron
```sh
#!/bin/bash

# cron wrapper script
#
# 0 4 * * 1,3,4,5,6,7 /bin/bash /home/voloshin/presseportal/presseportal/bin/tools/viperTester.sh

DIR=$(dirname "${BASH_SOURCE[0]}")
LOG=$DIR/logs/viperTester.log

if [[ ! -e $DIR/logs ]]; then
  mkdir -p $DIR/logs
fi

echo "`date` Started cron" >> $LOG 2>&1
echo "---" >> $LOG 2>&1

/usr/local/php5538/bin/php $DIR/viperTester.php >> $LOG 2>&1

echo "" >> $LOG 2>&1
echo "---" >> $LOG 2>&1
echo "`date` Cron cmd is done." >> $LOG 2>&1
```
