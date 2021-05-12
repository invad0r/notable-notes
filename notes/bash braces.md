---
tags: [shell/bash]
title: bash braces
created: '2019-09-24T06:43:14.231Z'
modified: '2021-05-12T08:46:50.982Z'
---

# bash braces

> `$` character introduces parameter expansion, command substitution, or arithmetic expansion

## usage 
```sh
# subshell
$(...)        # execute the command in the parens in a subshell and return its stdout
(...)         # run the commands listed in the parens in a subshell


# group
{...}         # execute the commands in the braces as a group
COMMAND | { echo "nope"; exit 1; }


# arithmetic expansion
$((...))          # arithmetic expansion and return the result
$((1+1))
$((2*2))
$((4/2))
$((2**2))
$((base#number))  # convert number from base to decimal
$((2#1111))       # 15
$((8#16))         # 14
$((16#FF))        # 255


${...}        # parameter expansion and return the value


# brace expansion - used to generate stings 
# consists of a sequence or a comma separated list of items inside curly braces `{}`
# sequence consists of a starting and ending-item separated by `..`
{aa,bb,cc,dd}      # aa bb cc dd
{0..12}            # 0 1 2 3 4 5 6 7 8 9 10 11 12
{3..-2}            # 3 2 1 0 -1 -2
{a..g}             # a b c d e f g
{g..a}             # g f e d c b a
a{0..3}b           # a0b a1b a2b a3b
{a,b{1..3},c}      # a b1 b2 b3 c

echo file{1,2,3}.txt
ls -l /etc/{resolv.conf, passwd}
```

## see also
- [[bash arithmetic expansion]]
- [[bash parameter expansion]]
- [double-parenthesis-with-and-without-dollar - stackoverflow](https://stackoverflow.com/a/31255942/2087704)
- [linuxjournal.com/bash-brace-expansion](https://www.linuxjournal.com/content/bash-brace-expansion)
