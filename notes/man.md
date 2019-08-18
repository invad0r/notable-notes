---
tags: [linux]
title: man
created: '2019-07-30T06:19:49.175Z'
modified: '2019-07-30T09:08:18.457Z'
---

# man

[The Linux man-pages project](https://www.kernel.org/doc/man-pages/)

```sh
aproppos namespace    # searches for man pages with namespaces
```

```sh
apt-get install man-db

export MANPAGER=less
```

## manpage locations
```sh
MANPATH /usr/man
MANPATH /usr/share/man
MANPATH /usr/local/man
MANPATH /usr/local/share/man
MANPATH /usr/X11R6/man
```

## bookmarks of important man-pages
```sh
man 7 signal    # list linux standart signals e.g. SIGSEGV

man ascii       # list ascii table

man 3 printf    # print ascii table and hex values

man 3 readline  # e.g. keymaps

man hier        # description of the filesystem hierarchy
```

## excerpt from `$ man man`
```sh
1   Executable programs or shell commands
2   System calls (functions provided by the kernel)
3   Library calls (functions within program libraries)
4   Special files (usually found in /dev)
5   File formats and conventions eg /etc/passwd
6   Games
7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)
8   System administration commands (usually only for root)
9   Kernel routines [Non standard]



1: User commands; man-pages includes a very few Section 1 pages that document programs supplied by the GNU C library.
2: System calls documents the system calls provided by the Linux kernel.
3: Library functions documents the functions provided by the standard C library.
4: Devices documents details of various devices, most of which reside in /dev.
5: Files describes various file formats, and includes proc(5), which documents the /proc file system.
7: Overviews, conventions, and miscellaneous.
8: Superuser and system administration commands; man-pages includes a very few Section 8 pages that document programs supplied by the GNU C library.

```
## colorize manpage
```sh
man() {
  env \
    LESS_TERMCAP_mb=$(printf "\e[1;31m") \
    LESS_TERMCAP_md=$(printf "\e[1;31m") \
    LESS_TERMCAP_me=$(printf "\e[0m") \
    LESS_TERMCAP_se=$(printf "\e[0m") \
    LESS_TERMCAP_so=$(printf "\e[1;44;33m") \
    LESS_TERMCAP_ue=$(printf "\e[0m") \
    LESS_TERMCAP_us=$(printf "\e[1;32m") \
    man "$@"
}
```
[Colorized man pages](http://boredzo.org/blog/archives/2016-08-15/colorized-man-pages-understood-and-customized)


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
