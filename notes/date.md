---
tags: [linux, osx]
title: date
created: '2019-07-30T06:19:49.033Z'
modified: '2019-11-27T12:26:20.319Z'
---

# date

> print or set the system date and time

## usage
```sh

date -r 1563533492792             # convert unix timestamp on osx

date -d "@1563533492792"          # convert unix timestamp on linux


date -u -d "$(date -d "8am")"     # convert local time to UTC

date -d "$(date -u -d "10am")"    # convert UTC time to local



date -v -11d                      # subtract 11 days from current date

date +"%m-%d-%y_%H-%M"            # formatting


date +%s        # get unix timestamp
```

```sh
man strftime
  # %F    is equivalent to ``%Y-%m-%d''.
  # %k    is replaced by the hour (24-hour clock) as a decimal number (0-23); single digits are preceded by a blank.
```

## see also
- [[timedatectl]]
- [[strftime]]
