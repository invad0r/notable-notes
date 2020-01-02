---
tags: [linux]
title: crontab
created: '2019-07-30T06:19:49.031Z'
modified: '2020-01-02T13:40:22.798Z'
---

# crontab

>  maintains crontab files for individual users

## usage
```sh
crontab -e    # edit crontab file, or create one if it doesn’t already exist.


crontab -l    # crontab list of cronjobs , display crontab file contents.

crontab -l | tee >(head -n1) | grep "^[^#;]"      # show only active jobs


crontab -r    # remove your crontab file.

crontab -v    # display the last time you edited your crontab file. (This option is only available on a few systems.)



crontab -u $USER -l                               # find out which user has a crontab

cat /var/spool/cron/crontabs/root                 # location of cron files for individual users


#    .---------------- minute (0 - 59)
#    |  .------------- hour (0 - 23)
#    |  |  .---------- day of month (1 - 31)
#    |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
#    |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7)  OR sun,mon,tue,wed,thu,fri,sat
#    |  |  |  |  |
#    *  *  *  *  *  USER command to be executed
#

 *     *     *     *     *    CMD          # every minute
00     *     *     *     *    CMD          # every hour
 */10  *     *     *     *    CMD          # every 10th minute
 0    22     *     *   1-5    CMD          # at 22:00 on every day-of-week from Monday through Friday

30 18 * * * rm /path/dir/* > /cronlogs/file.log     # cron execution execution log  
```

## see also
- https://crontab.guru/
- [Location of the crontab file](http://unix.stackexchange.com/a/196010)
