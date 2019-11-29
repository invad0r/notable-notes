---
tags: [linux]
title: man
created: '2019-07-30T06:19:49.175Z'
modified: '2019-09-23T06:27:34.086Z'
---

# man

> format and display the on-line manual pages

## install
`apt-get install man-db`

## environment
```sh
MANPAGER=less

# manpage locations
MANPATH /usr/man
MANPATH /usr/share/man
MANPATH /usr/local/man
MANPATH /usr/local/share/man
MANPATH /usr/X11R6/man
```

## usage
```sh
man -k intro      # equivalent to apropos

man -f intro      # equivalent to whatis; lookup pages and print short description
```

## sections
```sh
man man     # on linux

1 User commands,executable programs, shell commands
  man-pages includes a very few Section 1 pages that document programs supplied by the GNU C library.

  man(1)

2 System calls (functions provided by the kernel)

3 Library calls (functions within program libraries)

  printf (3)    # print ascii table and hex values
  readline (3)  # e.g. keymaps

4 Devices documents details of various devices, most of which reside in /dev.

5 Files describes various file formats, and includes proc(5), which documents the /proc file system.

6 Games

7 Overviews, conventions, and miscellaneous. (including macro packages and conventions), e.g. man(7), groff(7)

  signal (7)     # list linux standart signals e.g. SIGSEGV
  ascii (7)      # list ascii table
  hier (7)      # layout of filesystems

8 System administration commands (usually only for root)

9 Kernel routines [Non standard]
```

## custom manpage
```sh
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
- [The Linux man-pages project](https://www.kernel.org/doc/man-pages/)
- [Colorized man pages](http://boredzo.org/blog/archives/2016-08-15/colorized-man-pages-understood-and-customized)
- [[apropos]]
- [[whatis]]
