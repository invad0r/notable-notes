---
tags: [linux]
title: crontab
created: '2019-07-30T06:19:49.031Z'
modified: '2020-09-01T12:56:04.468Z'
---

# crontab

> maintains crontab files for individual users

## usage
```sh
crontab FILE            # install crontab from FILE or stdin if the pseudo-filename `-' is given

crontab -e              # edit or create crontab file: /var/spool/cron/crontabs/USER

crontab -r              # remove your crontab file.

crontab -v              # display the last time you edited your crontab file. (This option is only available on a few systems.)

crontab -l              # crontab list of cronjobs , display crontab file contents.

crontab -u $USER -l     # find out which user has a crontab; see also /var/spool/cron/crontabs

crontab -l | tee >(head -n1) | grep "^[^#;]"      # show only active jobs

# log files
/var/lib/boot2docker/log/crond.log      # boot2docker
/var/spool/cron/crontabs/USER           # location of cron files for individual users

# example crontab file
#    .--------------------------- minute (0 - 59)
#    |     .--------------------- hour (0 - 23)
#    |     |     .--------------- day of month (1 - 31)
#    |     |     |     .--------- month (1 - 12) OR jan,feb,mar,apr ...
#    |     |     |     |     .--- day of week (0 - 6) (Sunday=0 or 7)  OR sun,mon,tue,wed,thu,fri,sat
#    |     |     |     |     |
#    *     *     *     *     *    USER CMD
#
#    *     *     *     *     *    CMD          # every minute; cron has a 60 sec granularity and can't go lower !
#    */10  *     *     *     *    CMD          # every 10th minute
#    00    *     *     *     *    CMD          # every hour
#    0    22     *     *   1-5    CMD          # at 22:00 on every day-of-week from Monday through Friday
#
#    30   18     *     *     *    rm /path/dir/* > /cronlogs/file.log     # cron execution log
#    0     9     *     *     *    USER [ -x /usr/lib/mailman/cron/disabled ] && /usr/lib/mailman/cron/disabled
```

## see also

- [[crond]]
- [[tree]]
- [[bash process substitution]]
- [[bash eval]]
- [crontab.guru](https://crontab.guru/)
- [Location of the crontab file](http://unix.stackexchange.com/a/196010)
