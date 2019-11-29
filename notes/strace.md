---
tags: [linux]
title: strace
created: '2019-08-28T21:18:23.708Z'
modified: '2019-10-23T14:44:30.179Z'
---

# strace

> Each line in the trace contains the system call name, followed  by  its arguments  in parentheses and its return value

## install
`apt install strace` `yum install strace`	 `dnf install strace`	

## usage
```sh
strace -i ls              # print instruction pointers

strace -r ls              # print timestamp


strace -c ls              # print sumary

strace -o output.txt ls   # save to output file


strace -p 1725            # process id
```

## trace syscall
```sh
strace -e open ls         # trace specific syscall
strace -e openat ls

strace -e trace=open,read ls /home
```

## see also
-
