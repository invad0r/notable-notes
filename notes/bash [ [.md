---
tags: [shell/bash/keyword]
title: 'bash [ ['
created: '2020-09-02T14:24:09.002Z'
modified: '2021-05-12T08:46:30.644Z'
---

# bash [ [

> execute conditional command - returns a status of 0 or 1
> expressions are composed of same primaries used by `test`

## usage
```sh
[[ EXPRESSION ]]


( EXPRESSION )    Returns the value of EXPRESSION
! EXPRESSION      True if EXPRESSION is false; else false
EXPR1 && EXPR2    True if both EXPR1 and EXPR2 are true; else false
EXPR1 || EXPR2    True if either EXPR1 or EXPR2 is true; else false

OPERATORS
`==`, `!=`      string to the right of operator is used as pattern and pattern matching is performed
`=~`            string to the right of operator is matched as a regular expression
`&&`, `||`      do not evaluate EXPR2 if EXPR1 is sufficient to determine the expression's value
```

## see also
- [[bash test []]
- [[bash built-in vs keyword]]
