---
tags: [shell]
title: env
created: '2020-01-17T07:48:51.293Z'
modified: '2023-03-27T05:23:16.856Z'
---

# env

> set environment and execute command, or print environment

## flag

```sh
-i            # execute utility with only those environment variables specified by name=value options, the environment inherited by env is ignored completely
-P ALTPATH    # search the set of directories as specified by altpath to locate the specified utility program, instead of using the value of the PATH environment variable
-S string     # split apart the given string into multiple strings, and process each of the resulting strings as separate arguments to the env utility
              # the -S option recognizes some special character escape sequences and also supports environment-variable substitution, as described below
-u name       # if environment variable name is in the environment, then remove it before processing the remaining options
              #   similar to unset command in sh(1).  The value for name must not include the ‘=’ character
-v            # print verbose information for each step of processing done by the env utility. Additional information will be printed if -v is specified multiple times
```

## usage

```sh
env         # print environment
```

## see also

- [[bash export]]
- [[bash]]
- [[bash shopt]]
- [[bash set]]
- [[envsubst]]
- [[printenv]]
