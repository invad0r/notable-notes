---
tags: [bash]
title: bash declare
created: '2019-07-30T06:19:48.996Z'
modified: '2020-01-29T07:20:03.171Z'
---

# bash declare

> `declare` and `typeset` are synonym

## usage
```sh
declare -r foo=bar        # readonly
  
declare -i                # integer
  
declare -a                # array

declare -a arr=('aa' 'bb' 'cc' 'dd' 'ee')
  
declare -A                # associative array !
  
declare -f                # function(s)
  
declare -x                # export
  
declare -x var=$value


## print all values of one type
declare -xp         #  exported vairables

declare -f          # list sourced functions

declare -F          # list only function names

declare -p          # show variables


declare -a                   # variables are treated as arrays

declare -A                   # variables are treated as associative arrays

declare -f                   # uses funtion names only

declare -F                   # displays function names without definitions

declare -i                   # the variables are treaded as integers

declare -r                   # makes the variables read-only

declare -x                   # marks the variables for export via the environment
```

## useful for identifying variables, environmental, ..
```sh
declare | grep foo      # foo=bar

declare | grep Colors   # Colors=([0]="purple" [1]="reddish-orange" [2]="light green")
```

## see also
- [[bash export]]
- [[bash typeset]]
- [[bash array]]
- [declareref - tldp.org](http://tldp.org/LDP/abs/html/declareref.html)
