---
tags: [container]
title: kubectx
created: '2020-10-09T09:19:33.429Z'
modified: '2022-02-02T13:52:37.089Z'
---

# kubectx

> switch between clusters

## usage

```sh
-c, --current             # show the current context name
-d NAME                   # delete context NAME ('.' for current-context)
-u, --unset               # unset the current context
-h, --help                # show this message
```

```sh
kubectx                   # list the contexts

kubectx NEW_NAME=NAME     # rename context NAME to NEW_NAME

kubectx NEW_NAME=.        # rename current-context to NEW_NAME,  won't delete the user/cluster entry that is used by the context

kubectx -c                # show current context

kubectx NAME              # switch to context NAME

kubectx -                 # switch to the previous context
```

## see also

- [[kubectl]]
- [[kubens]]
- [[k9s]]
