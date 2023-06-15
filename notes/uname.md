---
tags: [linux, macos]
title: uname
created: '2023-05-15T13:04:32.582Z'
modified: '2023-05-24T08:38:59.420Z'
---

# uname

> display information about the system

## install

```sh
brew install coreutils
```

## option

```sh
-a      # behave as though options -m, -n, -r, -s, and -v were specified
-m      # write type of current hardware platform to STDOUT (make(1) uses it to set MACHINE variable)
-n      # write name of system to STDOUT
-o      # synonym for the -s option, for compatibility with other systems
-p      # write type of machine processor architecture to STDOUT (make(1) uses it to set MACHINE_ARCH variable)
-r      # write current release level of operating system to STDOUT
-s      # write name of operating system implementation to STDOUT
-v      # write version level of this release of operating system to STDOUT
```

## usage

```sh
uname -m

uname -a
```

## see also

- [[coreutils]]
- [[make]]
