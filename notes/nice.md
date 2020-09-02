---
tags: [coreutils]
title: nice
created: '2020-08-06T09:43:52.727Z'
modified: '2020-09-01T12:44:58.465Z'
---

# nice

> execute a utility at an altered scheduling priority

## usage
```sh
nice -n 5 date                  # execute `date` at priority 5 assuming the priority of the shell is 0

nice -n 16 nice -n -35 date     # execute `date` at priority -19 assuming the priority of the shell is 0 and you are the super-user
```

## see also
- [[nohup]]
