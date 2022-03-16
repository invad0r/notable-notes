---
tags: [shell/bash/builtin]
title: bash shopt
created: '2019-07-30T06:19:49.237Z'
modified: '2022-02-10T09:18:43.410Z'
---

# bash shopt

> set and unset shell options

    Change the setting of each shell option OPTNAME.  Without any option
    arguments, list each supplied OPTNAME, or all shell options if no
    OPTNAMEs are given, with an indication of whether or not each is set.


Historically, the `set` was used to turn options on and off. As the number of options grew, `set` became more difficult to use because options are represented by single letter codes. 
As a result, bash provides the `shopt` command to turn options on and off by name instead of a letter. 

## usage

```sh
-o        # restrict OPTNAMEs to those defined for use with `set -o'
-p        # print each shell option with an indication of its status
-q        # suppress output
-s        # enable (set) each OPTNAME
-u        # disable (unset) each OPTNAME
```

```sh
shopt -p                # print all options
shopt -p cdspell        # same as `unset -u`
shopt -p promptvars     # same as `set -s`

shopt -s histappend     # closing session will appended to HISTFILE rather than overwriting it
```

## see also

- [[bash]]
- [[bash set]]
- [[bash unset]]
- [[bash history]]
- [[env]]
