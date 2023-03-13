---
tags: [shell/bash/builtin]
title: bash test
created: '2019-07-30T06:19:49.021Z'
modified: '2022-06-02T12:09:52.169Z'
---

# bash test

> evaluate conditional expression - `[` synonym for `test` where last argument of opening `[` must be a literal `]`

## operators

```sh
-a            # and operator inside a test conditional expression
-o            # or operator inside a test conditional expression

-z STRING     # true if string is empty
-n STRING     # true if string is not empty

-o OPTION      # true if the shell option OPTION is enabled
-v VAR         # true if the shell variable VAR is set
-R VAR         # true if the shell variable VAR is set and is a name reference

-a FILE       # true if file exists
-e FILE       # true if file exists
-b FILE       # true if file is block special
-c FILE       # true if file is character special
-d FILE       # true if file is a directory
-f FILE       # true if file exists and is a regular file
-g FILE       # true if file is set-group-id
-h FILE       # true if file is a symbolic link
-L FILE       # true if file is a symbolic link
-k FILE       # true if file has its `sticky' bit set
-p FILE       # true if file is a named pipe
-r FILE       # true if file is readable by you
-s FILE       # true if file exists and is not empty
-S FILE       # true if file is a socket
-t FD         # true if FD is opened on a terminal
-u FILE       # true if the file is set-user-id
-w FILE       # true if the file is writable by you
-x FILE       # true if the file is executable by you
-O FILE       # true if the file is effectively owned by you
-G FILE       # true if the file is effectively owned by your group
-N FILE       # true if the file has been modified since it was last read
```

## usage

```sh
help test
help [


[ CMD ] && CMD || CMD

[ "$(echo 'ok')" ] && { echo 'success'; echo 'success'; } || { echo 'fail'; echo 'fail'; }    # notic space between curly-braces

test 3 == "$(kustomize build $OVERLAYS/staging | grep 5276h4th55 | wc -l)"; echo "$?"

if [ CMD ]; then CMD; fi

[ STRING1 =  STRING2 ]        # STRING1 matches STRING2
[ STRING1 != STRING2 ]        # STRING1 does not match STRING2
[ STRING1 <  STRING2 ]        # STRING1 is less STRING2
[ STRING1 >  STRING2 ]        # STRING1 is greater than STRING2

[ test -n STRING1 ]           # STRING1 is non-zero length (has length greater than 0)
[ test -z STRING1 ]           # STR1 is zero-length (has length 0)

[[ STRING1 == "STRING2" ]]    # variables don't have to be quoted => Bash performs word splitting and pathname expansion
[[ STRING1 =  "STRING2" ]]    # variables don't have to be quoted
[ "STRING1" == "STRING2" ]    # no word splitting and pathname expansion
[ "STRING1" =  "STRING2" ]


[ FILE1 -nt FILE2 ]          # FILE1 is newer than FILE2
[ FILE1 -ot FILE2 ]          # FILE1 is older than FILE2

# integer - INT1 and INT2 may be positive or negative
[ INT1 -lt INT2 ]            # less than
[ INT1 -le INT2 ]            # less than or equal
[ INT1 -eq INT2 ]            # equal
[ INT1 -ge INT2 ]            # greater than or equal
[ INT1 -gt INT2 ]            # greater than
[ INT1 -ne INT2 ]            # not equal

[ INT1 <= INT2 ]               # INT1 is less than or equal to INT2
[ INT1 >= INT2 ]               # INT1 is greater than or equal to INT2
```

## see also

- [[bash [ []]
- [[bash built-in vs keyword]]
- [[bash if]]
- [[bash arithmetic]]
- [tldp.org/LDP/abs/html/comparison-ops.html](https://tldp.org/LDP/abs/html/comparison-ops.html)
- [How to check if a variable is set in Bash?](https://stackoverflow.com/questions/3601515/how-to-check-if-a-variable-is-set-in-bash)
