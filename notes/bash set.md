---
tags: [bash/built-in]
title: bash set
created: '2019-07-30T06:19:49.019Z'
modified: '2020-01-17T07:52:29.223Z'
---

# bash set
> modify shell behavior - `set` or `unset` values of shell options and positional parameters

## usage
```sh
set 1 2 3 | echo $@     # set positional params

## shell behavior
set -o                  # print all options

$-                      # prints The current set of options in your current shell

# set                   # unset
set -o OPTION           set +o OPTION
set -x                  set +x

### options
# set -o OPTION         shorthand
set -o allexport        set -a
set -o braceexpand      set -B
set -o emacs
set -o errexit          set -e
set -o errtrace         set -E               # exit on error
set -o functrace        set -T
set -o hashall          set -h
set -o histexpand       set -H
set -o history                              # e.g. using `fc` when not sourcing script 
set -o ignoreeof
set -o keyword          set -k
set -o monitor          set -m                # enable jobcontrol => fg/bg
set -o noclobber        set -C
set -o noexec           set -n
set -o noglob           set -f
set -o nolog
set -o notify           set -b
set -o nounset          set -u
set -o onecmd           set -t
set -o physical         set -P
set -o pipefail
set -o posix
set -o privileged       set -p
set -o verbose          set -v
set -o vi
set -o xtrace           set -x
```

## see also
- [[bash unset]]
- [[env]]
- [Set and Shopt - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/425642/193945)
- [Bash Reference Manual: Modifying Shell Behavior](https://www.gnu.org/software/bash/manual/html_node/Modifying-Shell-Behavior.html)
- [What does $- mean in Bash? - Stack Overflow](https://stackoverflow.com/a/42757277/2087704)
