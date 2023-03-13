---
tags: [shell/bash/keyword]
title: 'bash [['
created: '2020-09-02T14:24:09.002Z'
modified: '2022-11-25T10:53:23.523Z'
---

# bash \[\[

> execute conditional command - returns a status of `0` or `1`
> EXPRESSION are composed of same primaries used by [[bash test]]

## usage

```sh
[[ EXPRESSION ]]


( EXPRESSION )    # returns value of EXPRESSION
! EXPRESSION      # true if EXPRESSION is false; else false
EXPR1 && EXPR2    # true if both EXPR1 and EXPR2 are true; else false
EXPR1 || EXPR2    # true if either EXPR1 or EXPR2 is true; else false

OPERATORS
`==`, `!=`        # string to the right of operator is used as pattern and pattern matching is performed
`=~`              # string to the right of operator is matched as a regular expression
`&&`, `||`        # do not evaluate EXPR2 if EXPR1 is sufficient to determine the expression's value
```

## see also

- [[bash test]]
- [[bash built-in vs keyword]]
