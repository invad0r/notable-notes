---
tags: [shell/bash]
title: bash globbing
created: '2019-07-30T06:19:49.009Z'
modified: '2022-04-27T14:23:05.524Z'
---

# bash globbing

> wildcards aka `pathname-expansion` refered to as `globbing`
> pathname-expansion expands: `*`, `?`, `.`, `[..]`

## usage

```sh
man bash           # some globbing explained

# wildcards
#   *       Matches any string, including the null string
#   ?       Matches any single (one) character
#   [...]   Matches any one of the enclosed characters


ls *.jpg        # list all jpg files

ls ?.jpg        # list jpg files with 1 char names (eg `a.jpg`, `1.jpg`)

rm [A-Z]*.jpg   # rm jpg files that start with a capital letter

# dotglob
# if set, bash includes filenames beginning with a `.` in the results of pathname expansion
shopt -s extglob          # set extended globbint
shopt -u dotglob          # unset dotglob


# extended globbing - `shopt -s extglob`
#   ?(pattern-list)     Matches zero or one occurrence of the given patterns
#   *(pattern-list)     Matches zero or more occurrences of the given patterns
#   +(pattern-list)     Matches one or more occurrences of the given patterns
#   @(pattern-list)     Matches one of the given patterns
#   !(pattern-list)     Matches anything except one of the given patterns


ls +(ab|def)*+(.jpg|.gif)               # list all the jpg and gif files that start with either "ab" or "def
ls ab*.jpg ab*.gif def*.jpg def*.gif    # without extended globbing

ls ab+(2|3).jpg                         # list all files that match regex "ab(2|3)+.jpg"

# list all the files that aren't jpgs or GIFs
ls *!(.jpg|.gif)         # wrong ".jpg" and the ".gif" of any file's name end up getting matched by the "*" and the null string at the end of the file
ls !(*.jpg|*.gif)        # right

ls !(+(ab|def)*+(.jpg|.gif))            # list all the files that aren't jpg or gif files and start with either "ab" or "def"
```

## see also

- [[bash shopt]]
- [[bash parameter expansion]]
- [linuxjournal.com/content/bash-extended-globbing](https://www.linuxjournal.com/content/bash-extended-globbing)
- [Path name expansion - Linux Shell Scripting Tutorial - A Beginner's handbook](http://bash.cyberciti.biz/guide/Path_name_expansion)


