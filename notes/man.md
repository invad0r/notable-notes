---
tags: [linux, macos]
title: man
created: '2019-07-30T06:19:49.175Z'
modified: '2023-05-19T11:32:48.783Z'
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
MANPAGER          # pager e.g. less
MANPAGER=vim -M +MANPAGER --not-a-term -
MANROFFSEQ        # see -p
MANSECT           # see -S
```

## option

```sh
-M                # manpath Forces a specific colon separated manual path instead of the default search path.  See manpath(1).  Overrides the MANPATH environment variable
-P                # use specified pager, defaults to "less -sR" if color support is enabled, or "less -s".  Overrides the MANPAGER environment variable, which in turn overrides the PAGER environment variable
-S                # mansect Restricts manual sections searched to the specified colon delimited list, default "1:8:2:3:3lua:n:4:5:6:7:9:l"
-a                # display all manual pages instead of just the first found for each page argument
-d                # print extra debugging information
-f                # emulate whatis
-h                # display short help message and exit
-k                # emulate apropos
-m arch[:machine] # override the default architecture and machine settings allowing lookup of other platform specific manual pages.  This option is accepted, but not implemented, on macOS
-o                # force use of non-localized manual pages.  See IMPLEMENTATION NOTES for how locale specific searches work.  Overrides the LC_ALL, LC_CTYPE, and LANG environment variables
-p [eprtv]        # use the list of given preprocessors before running nroff(1) or troff(1). ARG: e eqn(1), p pic(1), r refer(1), t tbl(1), v vgrind(1
-t                # send manual page source through troff(1) allowing transformation of the manual pages to other formats
-w                # display the location of the manual page instead of the contents of the manual page

# Options that apropos and whatis understand
-d      # Same as the -d option for man.
-s      # Same as the -S option for man.
```

## usage

```sh
man man                   # manual to man and show sections

man -k . | grep '(2)'     # list system calls

man -k intro              # equivalent to apropos
man -f intro              # equivalent to whatis; lookup pages and print short description

man 7 ascii               # show ascii tables, in case ascii command is present
```

## sections

```sh
#     macos                              linux
1.    General Commands                   User commands,executable programs, shell commands
2.    System Calls                       System calls (functions provided by the kernel)
3.    Library Functions                  Library calls (functions within program libraries)
4.    Kernel Interfaces                  Devices documents details of various devices, most of which reside in /dev.
5.    File Formats                       Files describes various file formats, and includes proc(5), which documents the /proc file system.
6.    Games                              Games
7.    Miscellaneous Information          Overviews, conventions, and miscellaneous. (including macro packages and conventions)
8.    System Manager's                   System administration commands (usually only for root)
9.    Kernel Developer's                 Kernel routines [Non standard] 
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

- [[c]], [[go]], [[rust]], [[java]]
- [[apropos]], [[whatis]]
- [[brew]]
- [[less]], [[more]]
- [[asdf]]
- [The Linux man-pages project](https://www.kernel.org/doc/man-pages/)
- [Colorized man pages](http://boredzo.org/blog/archives/2016-08-15/colorized-man-pages-understood-and-customized)
- [[command-not-found]]
- [[bash help]]
