---
tags: [bash]
title: bash io-redirects
created: '2019-07-30T06:19:49.011Z'
modified: '2019-08-19T14:31:13.254Z'
---

# bash io-redirects

[[tee]]

```sh
cmd1|cmd2  # pipe; takes standard output of cmd1 as standard input to cmd2
> file     # directs standard output to file
< file     # takes standard input from file
>> file    # directs standard output to file; append to file if it already exists
>|file     # forces standard output to file even if noclobber is set
n>|file    # forces output to file from file descriptor n even if noclobber is set
<> file    # uses file as both standard input and standard output
n<>file    # uses file as both input and output for file descriptor n

<<label    # here-document

n>file     # directs file descriptor n to file
n<file     # takes file descriptor n from file
n>>file    # directs file description n to file; append to file if it already exists
```

```sh
n>&        # duplicates standard output to file descriptor n
n<&        # duplicates standard input from file descriptor n
n>&m       # file descriptor n is made to be a copy of the output file descriptor
n<&m       # file descriptor n is made to be a copy of the input file descriptor
&>file     # directs standard output and standard error to file

<&-        # closes the standard input
>&-        # closes the standard output
n>&-       # closes the ouput from file descriptor n
n<&-       # closes the input from file descripor n
```
