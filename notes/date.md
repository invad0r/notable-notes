---
tags: [linux, osx]
title: date
created: '2019-07-30T06:19:49.033Z'
modified: '2019-08-20T08:44:23.924Z'
---

# date

```sh
man strftime
  # %F    is equivalent to ``%Y-%m-%d''.
  # %k    is replaced by the hour (24-hour clock) as a decimal number (0-23); single digits are preceded by a blank.
```

```sh
date -v -11d      # subtract 11 days from current date
```

## formatting
```sh
date +"%m-%d-%y_%H-%M"
```

## convert UTC

```sh
# convert a local time to UTC
date -u -d "$(date -d "8am")"

# a UTC time to local
date -d "$(date -u -d "10am")"
```

## convert unix timestamp
```sh
date -r 1563533492792
```
