---
tags: [bash]
title: bash declare
created: '2019-07-30T06:19:48.996Z'
modified: '2019-08-18T19:48:38.694Z'
---

# bash declare

`declare` and [[bash typeset]] are synonym

```sh
declare -r foo=bar        # readonly
  
declare -i                # integer
  
declare -a                # array
  
declare -A                # associative array !
  
declare -f                # function(s)
  
declare -x                # export
  
declare -x var=$value
```

## print all values of one type
```sh
declare -xp         #  exported vairables

declare -f          # list sourced functions

declare -F          # list only function names

declare -p          # show variables

```

```sh
declare -a                   # variables are treated as arrays

declare -A                   # variables are treated as associative arrays

declare -f                   # uses funtion names only

declare -F                   # displays function names without definitions

declare -i                   # the variables are treaded as integers

declare -r                   # makes the variables read-only

declare -x                   # marks the variables for export via the environment
```
http://tldp.org/LDP/abs/html/declareref.html


## useful for identifying variables, environmental, ..
```sh
declare | grep HOME
HOME=/home/bozo


zzy=68
declare | grep zzy
zzy=68


Colors=([0]="purple" [1]="reddish-orange" [2]="light green")
echo ${Colors[@]}
purple reddish-orange light green
declare | grep Colors
Colors=([0]="purple" [1]="reddish-orange" [2]="light green")
```
