---
title: pgrep
created: '2023-03-22T08:18:20.842Z'
modified: '2023-03-22T08:18:47.841Z'
---

# pgrep

> find signal processes by name

## flag

```sh
 -f         # match against full argument lists.  The default is to match against process names
 -l         # long output.  For pgrep, print the process name in addition to the process ID for each matching process.  
            #    If used in conjunction with -f, print the process ID and the full argument list for each matching process.  
            #    For pkill, display the kill command used for each process killed.
```

## usage

```sh
pgrep -fl PROCESS_NAME
```

## see also

- [[procps]]
- [[pkill]]
- [[grep]]
- [[bash kill]]
- [[ps]]
