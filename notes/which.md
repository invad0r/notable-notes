---
tags: [linux]
title: which
created: '2020-01-15T09:27:59.855Z'
modified: '2022-02-02T10:04:31.844Z'
---

# which

> locate a command

## usage

```sh
which -a CMD   # print all matching pathnames of each argument
```

## exit status

```sh
0      # if all specified commands are found and executable
1      # if one or more specified commands is nonexistent or not executable
2      # if an invalid option is specified
```

## see also

- [[file]]
- [[bash type]]
- [[bash command]]
- [[bash hash]]
- [[bash test []] `test -x filename`
