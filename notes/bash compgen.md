---
tags: [shell/bash/builtin]
title: bash compgen
created: '2019-08-02T06:13:41.072Z'
modified: '2021-05-12T08:46:07.674Z'
---

# bash compgen

> display possible completions depending on the options

## usage
```sh
# environment variables
COMPREPLY     # array variable used to store the completions
COMP_WORDS    # array of all words typed after the name of the program the compspec belongs to
COMP_CWORD    # index of COMP_WORDS array pointing to the word the current cursor is at 
              # - index of the word the cursor was when the tab key was pressed          
COMP_LINE     # the current command line

#   -d     names of directory
#   -e     names of exported shell variables
#   -f     names of file and functions
#   -g     names of groups
#   -j     names of job
#   -s     names of service
#   -u     names of userAlias names
#   -v     names of shell variables

compgen -c                     # list all the commands you could run
compgen -c x                   # names of all commands starting with x

compgen -a                     # list all the aliases you could run
compgen -a                     # names of alias, like alias but only alias names

compgen -b                     # list all the built-ins you could run
compgen -b                      # names of shell builtins => list-builtins, like help

compgen -k                     # list all the keywords you could run
compgen -k                      # names of Shell reserved words

compgen -A function            # list all the functions you could run
compgen -A function -abck      # list all the above in one go
compgen -A variable | grep X    # get all variables starting with X; see also: `echo ${!X*}`


compgen -W "now tomorrow never"
now
tomorrow
never

compgen -W "now tomorrow never" n
now
never

compgen -W "now tomorrow never" t
tomorrow
```

## see also
- [[bash]]
- [[bash type]]
