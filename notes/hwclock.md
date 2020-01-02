---
tags: [linux]
title: hwclock
created: '2019-12-05T07:04:33.069Z'
modified: '2019-12-30T07:36:17.392Z'
---

# hwclock

> hwclock - query and set the hardware clock (RTC) 

## usage
```sh
hwclock

hwclock --systohc --debug   # what it does when we copy system time to hardware time.

hwclock -hctosys --debug    # what it does when we copy hardware time to system time.
```

## see also
- [[date]]
- [[chronyc]]
