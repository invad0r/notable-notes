---
tags: [bash/built-in]
title: bash pwd
created: '2019-08-02T06:42:37.618Z'
modified: '2020-01-10T10:17:09.653Z'
---

# bash pwd

> Print the name of the current working directory.

## options
```sh
pwd -L     # print the value of $PWD if it names the current working directory

pwd -P     # print the physical directory, without any symbolic links
```

## script path
```sh
SCRIPTPATH="$( cd "$(dirname "$0")" ; pwd -P )"

DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"
```

## see also
- [reliable-way-for-a-bash-script-to-get-the-full-path](https://stackoverflow.com/questions/4774054/reliable-way-for-a-bash-script-to-get-the-full-path-to-itself/4774063)
