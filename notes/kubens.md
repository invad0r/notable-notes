---
tags: [container]
title: kubens
created: '2020-10-12T10:37:20.976Z'
modified: '2023-04-11T20:19:40.337Z'
---

# kubens

> switch between kubernetes namespaces

## install

```sh
brew install derailed/k9s/k9s
```

## option

```sh
-c, --current             # show the current namespace
-h, --help                # show this message
```

## usage

```sh
kubens                    # list the namespaces in the current context

kubens NAME               # change the active namespace of current context

kubens -                  # switch to the previous namespace in this context
```

## see also

- [[kubectl]]
- [[kubectx]]
- [[k9s]]
