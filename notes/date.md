---
tags: [linux, macos]
title: date
created: '2019-07-30T06:19:49.033Z'
modified: '2020-02-04T12:25:22.750Z'
---

# date

> print or set the system date and time

## usage
```sh

date -r 1563533492792             # convert unix timestamp on macos

date -d "@1563533492792"          # convert unix timestamp on linux


date -u -d "$(date -d "8am")"     # convert local time to UTC

date -d "$(date -u -d "10am")"    # convert UTC time to local



date -v -11d                      # subtract 11 days from current date

date +"%m-%d-%y_%H-%M"            # formatting

date +%s                          # get unix timestamp

date +%F_%H-%M                    # 2020-01-30_13-16
```

```sh
man strftime
  # %F    is equivalent to ``%Y-%m-%d''.
  # %k    is replaced by the hour (24-hour clock) as a decimal number (0-23); single digits are preceded by a blank.
```

## see also
- [[hwclock]]
- [[timedatectl]]
- [[strftime]]
