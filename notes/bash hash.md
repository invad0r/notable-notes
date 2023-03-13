---
tags: [linux, macos, shell/bash/builtin]
title: bash hash
created: '2019-08-02T06:42:37.599Z'
modified: '2022-04-27T14:23:33.799Z'
---

# bash hash

> remember or display program locations

- bash checks the hash table for the name to find the executable
- there is no need to put the script in your PATH, unless you want it to be available in all new shells


## usage

```sh
hash                      # display current hash-table

hash -l                   # display hash-table in format that is usable as input

hash -p /foo.sh foo       # add command with path and alias

hash -d foo               # delete remembered location

hash -r                   # clear hash-tabl
```

## see also

- [[bash type]]
- [[bash command]]
- [[which]]
