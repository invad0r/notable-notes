---
tags: [linux, macos]
title: man
created: '2019-07-30T06:19:49.175Z'
modified: '2023-05-05T08:15:39.412Z'
---

# man

> format and display the on-line manual pages

## install

```sh
apt-get install man-db
```

## env

```sh
MANPATH           # manpage locations: /usr/man, /usr/share/man, /usr/local/man, /usr/local/share/man, /usr/X11R6/man
MANPAGER=less
MANPAGER=vim -M +MANPAGER --not-a-term -
```

## option

```sh

```

## usage

```sh
# on macos
1.   General Commands
2.   System Calls
3.   Library Functions
4.   Kernel Interfaces
5.   File Formats
6.   Games
7.   Miscellaneous Information
8.   System Manager's
9.   Kernel Developer's

#  on linux
1.   User commands,executable programs, shell commands
2.   System calls (functions provided by the kernel)
3 Library calls (functions within program libraries)
4 Devices documents details of various devices, most of which reside in /dev.
5 Files describes various file formats, and includes proc(5), which documents the /proc file system.
6 Games
7 Overviews, conventions, and miscellaneous. (including macro packages and conventions)
8 System administration commands (usually only for root)
9 Kernel routines [Non standard]
```

```sh
man -k . | grep '(2)'     # list system calls

man -k intro              # equivalent to apropos

man -f intro              # equivalent to whatis; lookup pages and print short description

man man           # show sections
```

## custom manpage

```sh
# creating custom man page and open with man
cat <<EOF > ./nuseradd
.\" Manpage for nuseradd.
.\" Contact vivek@nixcraft.net.in to correct errors or typos.
.TH man 8 "06 May 2010" "1.0" "nuseradd man page"
.SH NAME
nuseradd \- create a new LDAP user 
.SH SYNOPSIS
nuseradd [USERNAME]
.SH DESCRIPTION
nuseradd is high level shell program for adding users to LDAP server.  On Debian, administrators should usually use nuseradd.debian(8) instead.
.SH OPTIONS
The nuseradd does not take any options. However, you can supply username.
.SH SEE ALSO
useradd(8), passwd(5), nuseradd.debian(8) 
.SH BUGS
No known bugs.
.SH AUTHOR
Vivek Gite (vivek@nixcraft.net.in)
EOF

man ./nuseradd
```

## see also

- [[asdf]]
- [The Linux man-pages project](https://www.kernel.org/doc/man-pages/)
- [Colorized man pages](http://boredzo.org/blog/archives/2016-08-15/colorized-man-pages-understood-and-customized)
- [[apropos]]
- [[whatis]]
- [[command-not-found]]
- [[bash help]]
