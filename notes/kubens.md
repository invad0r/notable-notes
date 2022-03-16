---
tags: [container]
title: kubens
created: '2020-10-12T10:37:20.976Z'
modified: '2022-02-02T13:52:32.012Z'
---

# kubens

> switch between kubernetes namespaces

## usage

```sh
-c, --current             # show the current namespace
-h, --help                # show this message
```

```sh
kubens                    # list the namespaces in the current context

kubens NAME               # change the active namespace of current context

kubens -                  # switch to the previous namespace in this context
```

## see also

- [[kubectl]]
- [[kubectx]]
- [[k9s]]
