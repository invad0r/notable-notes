---
tags: [bash]
title: bash debugging
created: '2019-07-30T06:19:49.021Z'
modified: '2019-08-18T19:00:59.543Z'
---

# bash debugging

[[bash trap]]


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

## debugger
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
