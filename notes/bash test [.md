---
tags: [bash/built-in]
title: 'bash test ['
created: '2019-07-30T06:19:49.021Z'
modified: '2020-01-23T09:03:48.727Z'
---

# bash test [

> evaluate conditional expression

## usage
```sh
help test

# operator
-a                        # and operator inside a test conditional expression
-o                        # or operator inside a test conditional expression

# string
str1=str2                 # str1 matches str2
str1!=str2                # str1 does not match str2
str1<str2                 # str1 is less than str2
str1>str2                 # str1 is greater than str2
-n str1                   # str1 is non-zero length (has length greater than 0)
-z str1                   # str1 is zero-length (has length 0)

# file
-a file                   # file exists
-d file                   # file exists and is a directory
-e file                   # file exists; same -a
-f file                   # file exists and is a regular file (i.e., not a directory or other special type of file)
-r file                   # you have read permission
-r file                   # file exists and is not empty
-w file                   # your have write permission
-x file                   # you have execute permission on file, or directory search permission if it is a directory
-N file                   # file was modified since it was last read
-O file                   # you own file
-G file                   # file's group ID matches yours (or one of yours, if you are in multiple groups)
file1 -nt file2           # file1 is newer than file2
file1 -ot file2           # file1 is older than file2

# int
# arg1 and arg2 may be positive or negative integers
arg1 -lt arg2             # less than
arg1 -le arg2             # less than or equal
arg1 -eq arg2             # equal
arg1 -ge arg2             # greater than or equal
arg1 -gt arg2             # greater than
arg1 -ne arg2             # not equal
```

## see also
- [[bash arithmetic]]
- [[bash if]]
- [How to check if a variable is set in Bash?](https://stackoverflow.com/questions/3601515/how-to-check-if-a-variable-is-set-in-bash)
