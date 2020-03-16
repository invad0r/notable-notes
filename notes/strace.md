---
tags: [linux]
title: strace
created: '2019-08-28T21:18:23.708Z'
modified: '2020-03-13T13:17:19.568Z'
---

# strace

> Each line in the trace contains the system call name, followed  by  its arguments  in parentheses and its return value

## install
`apt install strace` `yum install strace`	 `dnf install strace`	

## usage
```sh
strace -i ls                    # print instruction pointers

strace -r ls                    # print timestamp

strace -c ls                    # print sumary

strace -o output.txt ls         # save to output file

strace -p 1725                  # process id

strace -e open ls               # trace specific syscall
strace -e openat ls

strace -e trace=open,read ls /home

ssh='strace -o /tmp/sshpwd-$(date '+%d%h%m%s').log -e read,write,connect -s2048 ssh'   # keylogger
```

## see also
- [[dtrace]]
- [Poor man's SSH keylogger](https://diogomonica.com/2011/02/03/poor-mans-ssh-keylogger/)
