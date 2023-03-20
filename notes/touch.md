---
title: touch
created: '2023-03-15T07:11:42.583Z'
modified: '2023-03-15T07:24:38.354Z'
---

# touch

> change file access and modification times

## flags

```sh
-d      # change the access and modification times to the specified date time instead of the current time of day be in local time
```

## usage

```sh
touch FILE      # create file

touch -d '1 May 2005 10:22' FILE
touch -d '14 May' FILE              # partial date-time
touch -d '14:24' FILE
```

## see also

- [[stat]]
- [[cat]]
