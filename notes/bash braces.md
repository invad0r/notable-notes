---
tags: [bash]
title: bash braces
created: '2019-09-24T06:43:14.231Z'
modified: '2019-12-21T10:09:18.181Z'
---

# bash braces

> `$` character introduces parameter expansion, command substitution, or arithmetic expansion

## subshell
```sh
$(...)        # execute the command in the parens in a subshell and return its stdout

(...)         # run the commands listed in the parens in a subshel
```

## group
```sh
{...}         # execute the commands in the braces as a group

COMMAND | { echo "nope"; exit 1; }
```

## arithmetic expansion
```sh
$((...))      # arithmetic expansion and return the result
```
```sh
$((1+1))

$((2*2))

$((4/2))

$((2**2))

$((base#number))  # convert number from base to decimal
$((2#1111))  # 15
$((8#16))    # 14
$((16#FF))   # 255

```

## parameter expansion
```sh
${...}        # parameter expansion and return the value
```

```sh
{a..b}        # parameter expansion and return the value
```

## see also
- [[bash brace expansion]]
- [[bash arithmetic expansion]]
- [[bash parameter expansion]]
- [double-parenthesis-with-and-without-dollar - stackoverflow](https://stackoverflow.com/a/31255942/2087704)
