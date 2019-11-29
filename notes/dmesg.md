---
tags: [linux]
title: dmesg
created: '2019-08-28T06:45:42.937Z'
modified: '2019-08-28T07:24:16.133Z'
---

# dmesg

> `display message or driver message` is a command on most Unix-like operating systems that prints the message buffer of the kernel.

## log file
`/var/log/dmesg`

## options
```sh
dmesg


dmesg -c      # clear dmesg buffer logs
              # -c, --read-clear            read and clear all messages

dmesg -T      # show timestamp
              # -T, --ctime                 show human readable timestamp (could be inaccurate if you have used SUSPEND/RESUME)

dmesg -u      # only userspace messages
              # -u, --userspace             display userspace messages

# -C, --clear                 clear the kernel ring buffer
# -D, --console-off           disable printing messages to console
# -d, --show-delta            show time delta between printed messages
# -e, --reltime               show local time and time delta in readable format
# -E, --console-on            enable printing messages to console
# -F, --file <file>           use the file instead of the kernel log buffer
# -f, --facility <list>       restrict output to defined facilities
# -H, --human                 human readable output
# -k, --kernel                display kernel messages
# -L, --color                 colorize messages
# -l, --level <list>          restrict output to defined levels
# -n, --console-level <level> set level of messages printed to console
# -P, --nopager               do not pipe output into a pager
# -r, --raw                   print the raw message buffer
# -S, --syslog                force to use syslog(2) rather than /dev/kmsg
# -s, --buffer-size <size>    buffer size to query the kernel ring buffer
# -t, --notime                don't print messages timestamp
# -w, --follow                wait for new messages
# -x, --decode                decode facility and level to readable string

# -h, --help     display this help and exit
# -V, --version  output version information and exit
```

## facility
```sh
dmesg -f user

#    kern - kernel messages
#    user - random user-level messages
#    mail - mail system
#  daemon - system daemons
#    auth - security/authorization messages
#  syslog - messages generated internally by syslogd
#     lpr - line printer subsystem
#    news - network news subsystem
```

## level
```sh
dmesg --level=err,warn

#  emerg - system is unusable
#  alert - action must be taken immediately
#   crit - critical conditions
#    err - error conditions
#   warn - warning conditions
# notice - normal but significant condition
#   info - informational
#  debug - debug-level messages
```

## see also
- [[sysctl]]
- [[syslog]]
