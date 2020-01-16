---
tags: [bash/built-in]
title: bash dirs
created: '2019-08-02T06:42:37.579Z'
modified: '2020-01-10T10:17:09.210Z'
---

# bash dirs

> Display directory stack.


## usage
```sh
dirs [-clpv] [+N] [-N]

    -c       # clear the directory stack by deleting all of the elements
    -l       # do not print tilde-prefixed versions of directories relative to your home directory
    -p       # print the directory stack with one entry per line
    -v       # print the directory stack with one entry per line prefixed with its position in the stack
```

## arguments

      +N        Displays the Nth entry counting from the left of the list
                shown by dirs when invoked without options, starting with zero.

      -N        Displays the Nth entry counting from the right of the list
                shown by dirs when invoked without options, starting with zero.

## vairable
```sh
$DIRSTACK
```

## see also
- [[bash popd]]
- [[bash pushd]]
