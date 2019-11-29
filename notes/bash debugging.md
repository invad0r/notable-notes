---
tags: [bash]
title: bash debugging
created: '2019-07-30T06:19:49.021Z'
modified: '2019-11-25T06:57:21.159Z'
---

# bash debugging

> some ways to debug shell-scripts

## variables
```sh
${BASH_SOURCE}
${LINENO}
${FUNCNAME[0]}
```

## flags
```sh
bash -n SCRIPT.sh     # don't run commands; check for syntax errors only
set -o noexec         # alternative option set inside script

bash -v SCRIPT.sh     # echo commands before running them
set -o verbose        # alternative option set inside script

bash -x SCRIPT.sh     # echo commands after command-line processing
set -o xtrace         # alternative option set inside script
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

## see also
- [[bash trap]]
- [Debugging](http://tldp.org/LDP/abs/html/debugging.html)
- https://wiki.bash-hackers.org/scripting/debuggingtips#making_xtrace_more_useful
