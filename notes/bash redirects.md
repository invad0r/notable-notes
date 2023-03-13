---
tags: [shell/bash]
title: bash redirects
created: '2019-07-30T06:19:49.011Z'
modified: '2022-06-16T11:00:39.820Z'
---

# bash redirects

## usage

```sh
# "pipe"
COMMAND1 | COMMAND2            # takes stdout of COMMAND1 as stdin to COMMAND2

# "redirect"
1> FILE              # directs stdout to FILE
> FILE               # directs stdout to FILE

CMD > FILE
CMD 1> FILE

< FILE               # takes stdin from FILE

>> FILE              # directs stdout to FILE; append to FILE if it already exists
>|FILE               # forces stdout to FILE even if noclobber is set
n>|FILE              # forces output to FILE from FILE descriptor n even if noclobber is set
<> FILE              # uses FILE as both stdin and stdout
n<>FILE              # uses FILE as both input and output for file descriptor n
```

## here-doc

```sh
[n]<<[-]word         # here-document
  here-document
delimiter

echo <<EOF> FILE
Hello World
EOF
```

## here-string

```sh
[n]<<< word          # here-string
```

```sh
<()                  # process substitution
< <()                  # process substitution

n>FILE               # directs FILE descriptor n to FILE
n<FILE               # takes FILE descriptor n from FILE
n>>FILE              # directs FILE description n to FILE; append to file if it already exists

&[FILEDESCRIPTOR]     # reference to value of filedescriptor

n>&                  # duplicates stdout to file descriptor n
n<&                  # duplicates stdin from file descriptor n
n>&m                 # file descriptor n is made to be a copy of the output file descriptor
n<&m                 # file descriptor n is made to be a copy of the input file descriptor
&>FILE               # directs stdout and standard error to FILE

<&-                  # closes the stdin
>&-                  # closes the stdout
n>&-                 # closes the ouput from FILE descriptor n
n<&-                 # closes the input from FILE descripor n


&>/dev/null         # shorthand for `1> /dev/null 2> /dev/null`

command 1>&- 2>&-           # http://www.cyberciti.biz/faq/how-to-redirect-output-and-errors-to-devnull/#comment-40252
job 1>&- 2>&-  &            # additional & at end of job to put it in backgrounds
command 1>&- 2>&-  &        # additional & at end of command to put it in backgrounds
```

## dash

> redirection from  stdin to stdout  or  stdout to stdin

```sh
cat -                           # redirects from stdin to stdout
echo "whatever" | cat -         # redirects from stdin to stdout
grep "foo" FILE | diff FILE2 -
```

## see also

- [[heredoc]]
- [[bash read]]
- [[bash readarray]]
- [[bash exec]]
- [[tee]]
- [[tar]]
- [[bash process substitution]]
- [tldp.org/special-chars.html](http://tldp.org/LDP/abs/html/special-chars.html#DASHREF2)
