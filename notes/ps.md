---
tags: [linux]
title: ps
created: '2019-07-30T06:19:49.218Z'
modified: '2019-09-23T06:30:44.531Z'
---

# ps

> prints a line of information about the current running login shell and any processes running under it

## install
`apt install procps`

## usage
```sh
ps -a           # selects all processes with a tty except session leaders

ps a --forest   # osx not supported !
ps fax

ps -C sleep

ps -u yourusername       # lists your processes


# all processes on the system
ps ax     # bsd-style
ps -e     # standard-style

# all processes on the system with UUID
ps aux    # bsd-style
ps -ef    # standard-style


    # a = show processes for all users
    # u = display the process's user/owner
    # x = also show processes not attached to a terminal
```

## format
```sh
ps -o KEYWORD

ps -o user,pid,time

ps -o user pid comm command

ps xawf -eo pid,user,cgroup,args
```

## snippets
```sh
ps aux | grep apache  | awk '{print $6/1024 " MB";}'    # Ram consumption per apache process
ps aux | grep "[f]nord"                                 # don't show grep in result
```

## pgrep
```sh
pgrep -f    #  search the full command line and not only the process name
      -l    # 
```

## pkill
```sh
pkill -f mediaboss  # match full path
```

## see also
- [ps man page](http://linuxcommand.org/lc3_man_pages/ps1.html)
