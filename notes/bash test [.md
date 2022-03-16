---
tags: [shell/bash/builtin]
title: 'bash test ['
created: '2019-07-30T06:19:49.021Z'
modified: '2022-02-10T10:05:09.129Z'
---

# bash test [

> evaluate conditional expression
> `[` synonym for `test` - last argument of opening `[` must be a literal `]`

## usage

```sh
help test
help [


[ CMD ] && CMD || CMD

[ "$(echo 'ok')" ] && { echo 'success'; echo 'success'; } || { echo 'fail'; echo 'fail'; }    # notic space between curly-braces

if [ CMD ]; then CMD; fi

# operator
-a                        # and operator inside a test conditional expression
-o                        # or operator inside a test conditional expression

# string
STRING1 =  STRING2                # STRING1 matches STRING2
STRING1 != STRING2                # STRING1 does not match STRING2
STRING1 <  STRING2                # STRING1 is less STRING2
STRING1 >  STRING2                # STRING1 is greater than STRING2

-n STRING1                   # STRING1 is non-zero length (has length greater than 0)
-z STRING1                   # STR1 is zero-length (has length 0)

[[ STRING1 == "STRING2" ]]    # variables don't have to be quoted => Bash performs word splitting and pathname expansion
[[ STRING1 =  "STRING2" ]]    # variables don't have to be quoted
[ "STRING1" == "STRING2" ]    # no word splitting and pathname expansion
[ "STRING1" =  "STRING2" ]

# file
-a FILE                   # FILE exists
-d FILE                   # FILE exists and is a directory
-e FILE                   # FILE exists; same -a
-f FILE                   # FILE exists and is a regular FILE (i.e., not a directory or other special type of FILE)
-r FILE                   # you have read permission
-r FILE                   # FILE exists and is not empty
-w FILE                   # your have write permission
-x FILE                   # you have execute permission on FILE, or directory search permission if it is a directory
-N FILE                   # FILE was modified since it was last read
-O FILE                   # user owns FILE
-G FILE                   # FILE's group ID matches yours (or one of yours, if you are in multiple groups)
FILE1 -nt FILE2           # FILE1 is newer than FILE2
FILE1 -ot FILE2           # FILE1 is older than FILE2

# integer - INTEGER1 and INTEGER2 may be positive or negative
INTEGER1 -lt INTEGER2             # less than
INTEGER1 -le INTEGER2             # less than or equal
INTEGER1 -eq INTEGER2             # equal
INTEGER1 -ge INTEGER2             # greater than or equal
INTEGER1 -gt INTEGER2             # greater than
INTEGER1 -ne INTEGER2             # not equal

INTEGER1 <= INTEGER2                # INTEGER1 is less than or equal to INTEGER2
INTEGER1 >= INTEGER2                # INTEGER1 is greater than or equal to INTEGER2

test 3 == "$(kustomize build $OVERLAYS/staging | grep 5276h4th55 | wc -l)"; echo "$?"
```

## see also

- [[bash [ []]
- [[bash built-in vs keyword]]
- [[bash if]]
- [[bash arithmetic]]
- [tldp.org/LDP/abs/html/comparison-ops.html](https://tldp.org/LDP/abs/html/comparison-ops.html)
- [How to check if a variable is set in Bash?](https://stackoverflow.com/questions/3601515/how-to-check-if-a-variable-is-set-in-bash)
