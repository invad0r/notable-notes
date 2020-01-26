---
tags: [bash]
title: bash
created: '2019-07-30T06:19:49.025Z'
modified: '2020-01-23T09:23:23.162Z'
---

# bash

> At its base, a shell is simply a `macro processor` that executes commands. The term `macro processor` means functionality where text and symbols are expanded to create larger expressions. 

## usage
```sh
bash -c "echo 1"   # -c read command-string

bash -i            # shell is interactive.

bash -l            # act as if it had been invoked as a login shell

bash -x            # dump what bash runs on startup http://superuser.com/a/144777


# variables
$0                      # current shell ?

$BASH

$BASH_VERSION           # As a string.

${BASH_VERSINFO[@]}     # As an array.

${FUNCNAME[@]}          # All functions including parents.
```

## see also
- [[env]]
- [[bash debugging.md]]
- [[bash parameter expansion]]
- [[bash built-in vs keyword]]
- [Bash Reference Manual](https://www.gnu.org/software/bash/manual/bash.html?#What-is-a-shell_003f)
- [pure-bash-bible - github.com](https://github.com/dylanaraps/pure-bash-bible)
