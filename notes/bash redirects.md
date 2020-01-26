---
tags: [bash]
title: bash redirects
created: '2019-07-30T06:19:49.011Z'
modified: '2020-01-26T17:06:12.637Z'
---

# bash redirects

```sh
cmd1|cmd2  # pipe; takes standard output of cmd1 as standard input to cmd2
> file     # directs standard output to file
< file     # takes standard input from file
>> file    # directs standard output to file; append to file if it already exists
>|file     # forces standard output to file even if noclobber is set
n>|file    # forces output to file from file descriptor n even if noclobber is set
<> file    # uses file as both standard input and standard output
n<>file    # uses file as both input and output for file descriptor n


[n]<<[-]word          # here-document
  here-document
delimiter

[n]<<< word           # here-string

<()       #  process substitution


n>file     # directs file descriptor n to file
n<file     # takes file descriptor n from file
n>>file    # directs file description n to file; append to file if it already exists



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

## redirection from/to stdin or stdout [dash]
```sh
cat -

echo "whatever" | cat -

file -

grep Linux file1 | diff file2 -
```

## see also
- [[tee]]
- [[tar]]
- [[bash process substitution]]
- [special-chars.html - tldp.org](http://tldp.org/LDP/abs/html/special-chars.html#DASHREF2)
