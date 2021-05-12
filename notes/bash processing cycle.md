---
tags: [shell/bash]
title: bash processing cycle
created: '2019-07-30T06:19:48.994Z'
modified: '2021-05-12T08:46:51.259Z'
---

# bash processing cycle

> The default order for command lookup is `functions`, followed by `built-ins`, with scripts and executables last.
> There are three built-ins that you can use to override this order: `command`, `builtin` and `enable`.

## usage
```sh
command  # removes alias and function lookup. Only built-ins and commands found in the search path are executed


builtin  # looks up only built-in commands, ignoring functions and commands found in PATH


enable   # enables and disables shell built-ins
```

## see also
- [[bash command]]
