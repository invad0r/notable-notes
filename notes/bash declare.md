---
tags: [shell/bash]
title: bash declare
created: '2019-07-30T06:19:48.996Z'
modified: '2022-02-10T09:13:33.034Z'
---

# bash declare

> set variable values and attributes

## usage

```sh
# print all values of one type
-xp         # exported vairables
-f          # list sourced functions
-F          # list only function names
-p          # show variables
-a          # variables are treated as arrays

-a          # array
-A          # variables are treated as associative arrays
-f          # uses funtion names only
-F          # displays function names without definitions
-i          # the variables are treaded as integers
-r          # makes the variables read-only
-x          # marks the variables for export via the environment
```

```sh
declare -r foo=bar        # readonly

declare -a arr=('aa' 'bb' 'cc' 'dd' 'ee')

declare -x var=$value

# useful for identifying variables, environmental, ..
declare | grep foo      # foo=bar
declare | grep Colors   # Colors=([0]="purple" [1]="reddish-orange" [2]="light green")
```

## see also

- [[bash export]]
- [[bash set]]
- [[bash unset]]
- [[bash typeset]]
- [[bash array]]
- [[bash readarray]]
- [declareref - tldp.org](http://tldp.org/LDP/abs/html/declareref.html)
