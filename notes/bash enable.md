---
tags: [bash/builtin]
title: bash enable
created: '2019-08-02T06:42:37.583Z'
modified: '2019-08-20T07:21:21.954Z'
---

# bash enable
> Enable and disable shell builtins.

[[bash builtin]]

## options
```sh
-a        print a list of builtins showing whether or not each is enabled
-n        disable each NAME or display a list of disabled builtins
-p        print the list of builtins in a reusable format
-s        print only the names of Posix `special' builtins
```
## options controlling dynamic loading
```sh
-f        Load builtin NAME from shared object FILENAME
-d        Remove a builtin loaded with -f
```
