---
title: go-cron
created: '2020-03-26T15:24:17.413Z'
modified: '2020-03-26T15:41:27.285Z'
---

# go-cron

## usage
```sh
exec go-cron -s "${SCHEDULE}" -- /usr/local/bin/backup
exec go-cron -s "0 */10 * * * *" -- /bin/bash -c 'backup.sh'
exec go-cron -s "0 0 3 * *" -- "backup.sh"

#  Field name   | Mandatory? | Allowed values  | Allowed special characters
#  ----------   | ---------- | --------------  | --------------------------
#  Seconds      | Yes        | 0-59            | * / , -
#  Minutes      | Yes        | 0-59            | * / , -
#  Hours        | Yes        | 0-23            | * / , -
#  Day of month | Yes        | 1-31            | * / , - ?
#  Month        | Yes        | 1-12 or JAN-DEC | * / , -
#  Day of week  | Yes        | 0-6 or SUN-SAT  | * / , - ?
```

## see also
- [[crontab]]
- [[go]]
- [cron - GoDoc](https://godoc.org/github.com/robfig/cron)
- [`odise/go-cron` golang wrapper over `robfig/cron` and `os/exec` as a cron](https://github.com/odise/go-cron)
