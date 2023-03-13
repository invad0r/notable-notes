---
tags: [shell/bash/builtin]
title: bash pwd
created: '2019-08-02T06:42:37.618Z'
modified: '2021-05-12T08:46:08.283Z'
---

# bash pwd

> print the name of the current working directory

## usage

```sh
pwd -L     # print the value of $PWD if it names the current working directory

pwd -P     # print the physical directory, without any symbolic links


SCRIPTPATH="$( cd "$(dirname "$0")" ; pwd -P )"                   # script path

CURRENT_DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"   # if `cd` works return current working dir
```

## see also

- [[basename dirname]]
- [reliable-way-for-a-bash-script-to-get-the-full-path](https://stackoverflow.com/questions/4774054/reliable-way-for-a-bash-script-to-get-the-full-path-to-itself/4774063)
