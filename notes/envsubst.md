---
tags: [linux]
title: envsubst
created: '2020-04-24T11:43:39.417Z'
modified: '2022-02-04T09:12:20.390Z'
---

# envsubst

> substitutes environment variables in shell format strings

## install

```sh
brew install gettext
apt install gettext-base
yum install gettext
```

## usage

```sh
-v, --variables      # output the variables occurring in SHELL-FORMAT
-h, --help           # display this help and exit
-V, --version        # output version information and exit
```

```sh
envsubst \$FOO,$\BAR < config.file > config.dist

echo '$HOME' | envsubst                       # replace env vars in STDIN and output to STDOUT

envsubst < path/to/input                      # replace env vars in an input file and output to STDOUT

envsubst < path/to/input > path/to/output     # replace env vars in an input file and output to a file

envsubst variables < path/to/input            # replace env vars in input from a space-separated list
```

## see also

- [[env]]
- [[sed]]
- [gnu.org/software/gettext/manual/gettext.html#envsubst-Invocation](https://www.gnu.org/software/gettext/manual/gettext.html#envsubst-Invocation)
