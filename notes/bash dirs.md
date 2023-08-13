---
tags: [shell/bash/builtin]
title: bash dirs
created: '2019-08-02T06:42:37.579Z'
modified: '2023-06-28T08:26:50.469Z'
---

# bash dirs

> display directory stack

## option

```sh
-c       # clear the directory stack by deleting all of the elements
-l       # do not print tilde-prefixed versions of directories relative to your home directory
-p       # print the directory stack with one entry per line
-v       # print the directory stack with one entry per line prefixed with its position in the stack
+N       # displays Nth entry counting from left  of the list shown by dirs starting with zero
-N       # displays Nth entry counting from right of the list shown by dirs starting with zero
```

## env

```sh
DIRSTACK
```

## usage

```sh
dirs
```

## see also

- [[bash popd]]
- [[bash pushd]]
