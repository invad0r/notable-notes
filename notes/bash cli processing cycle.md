---
tags: [bash]
title: bash cli processing cycle
created: '2019-07-30T06:19:48.994Z'
modified: '2019-08-01T07:20:15.368Z'
---

# bash cli processing cycle

> The default order for command lookup is `functions`, followed by `built-ins`, with scripts and executables last.
> There are three built-ins that you can use to override this order: `command`, `builtin` and `enable`.


```sh
command  # removes alias and function lookup. Only built-ins and commands found in the search path are executed
```

```sh
builtin  # looks up only built-in commands, ignoring functions and commands found in PATH
```

```sh
enable   # enables and disables shell built-ins
```
