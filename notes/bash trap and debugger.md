---
tags: [bash]
title: bash trap and debugger
created: '2019-07-30T06:19:49.021Z'
modified: '2019-07-30T06:22:29.802Z'
---

# bash trap and debugger

```sh
bash -n scriptname  # don't run commands; check for syntax errors only
set -o noexec       # alternative (set option in script)

bash -v scriptname  # echo commands before running them
set -o verbose      # alternative (set option in script)

bash -x scriptname  # echo commands after command-line processing
set -o xtrace       # alternative (set option in script)
```

## breakpoint
```sh
read var    # simple breakpoint
echo -e "dbg> \c"; read cmd; eval $cmd

$ dbg> doSomethingFunction
$ dbg> someVariable
```

## trap
```sh
trap 'echo "VARIABLE-TRACE> \$DOCKER_HOST= \"$DOCKER_HOST\""' DEBUG
```
```sh
trap cmd sig1 sig2  # executes a command when a signal is received by the script
trap "" sig1 sig2   # ignores that signals
trap - sig1 sig2    # resets the action taken when the signal is received to the default
```

```sh
# golang like defer
# https://twitter.com/TheNikhita/status/1061973769470795776
scratch=$(mktemp -d -t tmp.XXXXXXXX)
function finish {
  rm -rf "$scratch"
}
trap finish EXIT
```


```sh
trap 'echo $varname' EXIT  # useful when you want to print out the values of variables at the point that your script exits

function errtrap {
  es=$?
  echo "ERROR line $1: Command exited with status $es."
}

trap 'errtrap $LINENO' ERR  # is run whenever a command in the surrounding script or function exists with non-zero status

function dbgtrap {
  echo "badvar is $badvar"
}

trap dbgtrap DEBUG  # causes the trap code to be executed before every statement in a function or script
# ...section of code in which the problem occurs...
trap - DEBUG  # turn off the DEBUG trap

function returntrap {
  echo "A return occured"
}

trap returntrap RETURN  # is executed each time a shell function or a script executed with the . or source commands finishes executing
```

```sh
#!/bin/bash

echo "LINENO: $LINENO"

trap 'echo "VARIABLE-TRACE> \$variable = \"$variable\""' DEBUG  # Echoes the value of $variable after every command.

variable=29; line=$LINENO

echo "  Just initialized \$variable to $variable in line number $line."

let "variable *= 3"; line=$LINENO

echo "  Just multiplied \$variable by 3 in line number $line."

exit 0

#  The "trap 'command1 . . . command2 . . .' DEBUG" construct is
#+ more appropriate in the context of a complex script,
#+ where inserting multiple "echo $variable" statements might be
#+ awkward and time-consuming.

# Thanks, Stephane Chazelas for the pointer.


#    Output of script:
#
#    VARIABLE-TRACE> $variable = ""
#    VARIABLE-TRACE> $variable = "29"
#      Just initialized $variable to 29.
#    VARIABLE-TRACE> $variable = "29"
#    VARIABLE-TRACE> $variable = "87"
#      Just multiplied $variable by 3.
#    VARIABLE-TRACE> $variable = "87"
```
[Debugging](http://tldp.org/LDP/abs/html/debugging.html)
