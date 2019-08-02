---
tags: [bash]
title: bash declare
created: '2019-07-30T06:19:48.996Z'
modified: '2019-07-30T06:22:29.786Z'
---

# bash declare

`declare` and `typeset` are synonym

```sh
declare

  -r # readonly
  
  -i # integer
  
  -a # array
  
  -A # associative array !
  
  -f # function(s)
  
  -x # export
  
  -x var=$value

# just using the option prints all values of one type

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
