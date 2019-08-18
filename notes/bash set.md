---
tags: [bash, bash/builtin]
title: bash set
created: '2019-07-30T06:19:49.019Z'
modified: '2019-08-18T15:40:45.385Z'
---

# bash set

> modify shell behavior
> Set or unset values of shell options and positional parameters.

[[bash unset]]

```sh
set 1 2 3 | echo $@     # set positional params
```

## shell behavior

```sh
set -o   # print all options

$-      # prints The current set of options in your current shell.
```
[What does $- mean in Bash? - Stack Overflow](https://stackoverflow.com/a/42757277/2087704)

#### set / unset
```sh
# set             # unset
set -o OPTION     set +o OPTION
set -x            set +x
```

### options
```sh
# set -o OPTION        shorthand
set -o allexport       set -a
set -o braceexpand     set -B
set -o emacs
set -o errexit         set -e
set -o errtrace        set -E               # exit on error
set -o functrace       set -T
set -o hashall         set -h
set -o histexpand      set -H
set -o history                              # e.g. using `fc` when not sourcing script 
set -o ignoreeof
set -o keyword        set -k
set -o monitor        set -m                # jobcontrol => fg/bg
set -o noclobber      set -C
set -o noexec         set -n
set -o noglob         set -f
set -o nolog
set -o notify         set -b
set -o nounset        set -u
set -o onecmd         set -t
set -o physical       set -P
set -o pipefail
set -o posix
set -o privileged     set -p
set -o verbose        set -v
set -o vi
set -o xtrace         set -x
```

[bash - Set and Shopt - Why Two? - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/425642/193945)

[Bash Reference Manual: Modifying Shell Behavior](https://www.gnu.org/software/bash/manual/html_node/Modifying-Shell-Behavior.html)
