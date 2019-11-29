---
tags: [bash/builtin]
title: bash compgen
created: '2019-08-02T06:13:41.072Z'
modified: '2019-11-28T08:10:15.288Z'
---

# bash compgen

## usage
```sh
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

## env variables
```sh
COMPREPLY     # array variable used to store the completions

COMP_WORDS    # array of all words typed after the name of the program the compspec belongs to

COMP_CWORD    # index of COMP_WORDS array pointing to the word the current cursor is at 
              # - index of the word the cursor was when the tab key was pressed
              
COMP_LINE     # the current command line
```

```sh
compgen -c x    # Names of all commands starting with x

compgen -a      # Names of alias, like alias but only alias names

compgen -b      # Names of shell builtins => list-builtins, like help

compgen -k      # Names of Shell reserved words

-d    # Names of directory
-e    # Names of exported shell variables
-f    # Names of file and functions
-g    # Names of groups
-j    # Names of job

-s    # Names of service
-u    # Names of userAlias names
-v    # Names of shell variables
```

## see also
- [[bash built-in vs keyword]]
