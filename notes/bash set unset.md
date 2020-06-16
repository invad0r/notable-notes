---
tags: [bash/built-in]
title: bash set unset
created: '2019-07-30T06:19:49.019Z'
modified: '2020-05-06T06:59:37.764Z'
---

# bash set unset
> set/unset values and attributes of shell variables and functions.
> modify shell behavior - `set` or `unset` values of shell options and positional parameters

## usage
```sh
set 1 2 3 | echo $@                         # set positional params


# shell behavior
echo $-                                     # prints The current set of options in your current shell
set -o                                      # print all options

# set                   # unset
set -o OPTION           set +o OPTION
set -x                  set +x

# set -o OPTION         shorthand
set -o allexport        set -a              # each variable or function that is created/modified is given export-attribute and marked for export to the environment of subsequent commands. 
set -o braceexpand      set -B
set -o emacs
set -o errexit          set -e
set -o errtrace         set -E              # exit on error
set -o functrace        set -T
set -o hashall          set -h
set -o histexpand       set -H
set -o history                              # e.g. using `fc` when not sourcing script 
set -o ignoreeof
set -o keyword          set -k
set -o monitor          set -m              # enable jobcontrol => fg/bg
set -o noclobber        set -C
set -o noexec           set -n
set -o noglob           set -f              # disable filename-expansion "globbing"
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

unset           # Without options, unset first tries to unset a variable, and if that fails,tries to unset a function
                # Some variables cannot be unset; also see `readonly'.
unset -f        # treat each NAME as a shell function
unset -v        # treat each NAME as a shell variable
unset -n        # treat each NAME as a name reference and unset the variable itself rather than the variable it references

unset -v ${!DOCKER_*}   # unset all variables starting with DOCKER_
```

## see also
- [[env]]
- [[bash parameter expansion]]
- [Set and Shopt - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/425642/193945)
- [Bash Reference Manual: Modifying Shell Behavior](https://www.gnu.org/software/bash/manual/html_node/Modifying-Shell-Behavior.html)
- [What does $- mean in Bash? - Stack Overflow](https://stackoverflow.com/a/42757277/2087704)
