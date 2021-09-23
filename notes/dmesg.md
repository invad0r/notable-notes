---
tags: [linux]
title: dmesg
created: '2019-08-28T06:45:42.937Z'
modified: '2021-06-08T05:40:59.995Z'
---

# dmesg

> `display message or driver message` prints the message buffer of the kernel

## usage

```sh
-C, --clear                   # clear the kernel ring buffer
-c, --read-clear              # read and clear all messages
-D, --console-off             # disable printing messages to console
-d, --show-delta              # show time delta between printed messages
-e, --reltime                 # show local time and time delta in readable format
-E, --console-on              # enable printing messages to console
-F, --file FILE               # use the file instead of the kernel log buffer
-f, --facility LIST           # restrict output to defined facilities:
                              #     kern - kernel messages
                              #     user - random user-level messages
                              #     mail - mail system
                              #   daemon - system daemons
                              #     auth - security/authorization messages
                              #   syslog - messages generated internally by syslogd
                              #      lpr - line printer subsystem
                              #     news - network news subsystem
-H, --human                   # human readable output
-k, --kernel                  # display kernel messages
-L, --color                   # colorize messages
-l, --level LIST              # comma separated list of restrict output to defined levels:
                              #    emerg - system is unusable
                              #    alert - action must be taken immediately
                              #     crit - critical conditions
                              #      err - error conditions
                              #     warn - warning conditions
                              #   notice - normal but significant condition
                              #     info - informational
                              #    debug - debug-level messages
-n, --console-level LEVEL     # set level of messages printed to console
-P, --nopager                 # do not pipe output into a pager
-r, --raw                     # print the raw message buffer
-S, --syslog                  # force to use syslog(2) rather than /dev/kmsg
-s, --buffer-size SIZE        # buffer size to query the kernel ring buffer
-t, --notime                  # don't print messages timestamp
-T, --ctime                   # show human readable timestamp (could be inaccurate if you have used SUSPEND/RESUME)
-u, --userspace               # display userspace messages
-w, --follow                  # wait for new messages
-x, --decode                  # decode facility and level to readable string

-h, --help                    # display this help and exit
-V, --version                 # output version information and exit
```

```sh
/var/log/dmesg              # log file

dmesg

dmesg -c                    # clear dmesg buffer logs

dmesg -T                    # show timestamp

dmesg -u                    # only userspace messages

dmesg -f user               # facility

dmesg --level=err,warn
```

## see also
- [[sysctl]]
- [[syslog]]
