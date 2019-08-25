---
tags: [bash/builtin]
title: bash trap
created: '2019-08-02T06:42:37.638Z'
modified: '2019-08-20T07:21:21.983Z'
---

# bash trap

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
