---
tags: [bash]
title: bash redirects
created: '2019-07-30T06:19:49.011Z'
modified: '2020-07-16T07:05:51.133Z'
---

# bash redirects

```sh
cmd1|cmd2            # "pipe" takes stdout of cmd1 as stdin to cmd2

1> file              # directs stdout to file
> file               # directs stdout to file

CMD > OUTPUT
CMD 1> OUTPUT

< file               # takes stdin from file

>> file              # directs stdout to file; append to file if it already exists
>|file               # forces stdout to file even if noclobber is set
n>|file              # forces output to file from file descriptor n even if noclobber is set
<> file              # uses file as both stdin and stdout
n<>file              # uses file as both input and output for file descriptor n

[n]<<[-]word         # here-document
  here-document
delimiter

[n]<<< word          # here-string

<()                  # process substitution

n>file               # directs file descriptor n to file
n<file               # takes file descriptor n from file
n>>file              # directs file description n to file; append to file if it already exists

&[FILEDESCRIPTOR]     # reference to value of filedescriptor

n>&                  # duplicates stdout to file descriptor n
n<&                  # duplicates stdin from file descriptor n
n>&m                 # file descriptor n is made to be a copy of the output file descriptor
n<&m                 # file descriptor n is made to be a copy of the input file descriptor
&>file               # directs stdout and standard error to file

<&-                  # closes the stdin
>&-                  # closes the stdout
n>&-                 # closes the ouput from file descriptor n
n<&-                 # closes the input from file descripor n

# dash: redirection from   stdin to stdout  or  stdout to stdin
cat -                           # redirects from stdin to stdout
echo "whatever" | cat -         # redirects from stdin to stdout
grep "foo" file | diff file2 -
```

## see also
- [[bash exec]]
- [[tee]]
- [[tar]]
- [[bash process substitution]]
- [tldp.org/special-chars.html](http://tldp.org/LDP/abs/html/special-chars.html#DASHREF2)
