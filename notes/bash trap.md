---
tags: [shell/bash/builtin]
title: bash trap
created: '2019-08-02T06:42:37.638Z'
modified: '2022-02-10T10:09:42.974Z'
---

# bash trap

> Defines and activates handlers to be run when the shell receives signals or other conditions

## usage

```sh
trap -l       # print a list of signal names and their corresponding numbers

trap -p CMD   # display the trap commands associated with each SIGNAL_SPEC

trap 'echo "VARIABLE-TRACE> \$DOCKER_HOST= \"$DOCKER_HOST\""' DEBUG   # debugging

trap CMD sig1 sig2  # executes a command when a signal is received by the script

trap "" sig1 sig2   # ignores that signals

trap - sig1 sig2    # resets the action taken when the signal is received to the default
```

## signals

```sh
name       value            effect                    shortcut
--         --               --                        --
SIGHUP     1                Hangup                   
SIGINT     2                Interrupt from keyboard   ctrl + c
SIGKILL    9                Kill-Signal                             cannot be caught, blocked or ignored !
SIGTERM    15               Terminate-Signal        
SIGSTOP    17, 19, 23       Stop proc                 ctl + z       cannot be caught, blocked or ignored !
```

## go defer

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

## see also

- [[signal]]
- [[bash debugging]]
- [[mktemp]]
