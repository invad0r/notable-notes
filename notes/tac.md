---
tags: [linux, macos]
title: tac
created: '2022-06-17T09:24:48.712Z'
modified: '2023-03-25T12:25:53.994Z'
---

# tac

> concatenate and print files in reverse

## flags

```sh
-b, --before                # attach the separator before instead of after
-r, --regex                 # interpret the separator as a regular expression
-s, --separator=STRING      # use STRING as the separator instead of newline
    --help                  # display this help and exit
    --version               # output version information and exit
```

## usage

```sh
tac

kubectl get po --sort-by=.metadata.creationTimestamp | tac
```

## see also

- [[cat]]
- [[tig]]
- [[less]]
