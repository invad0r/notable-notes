---
tags: [container]
title: k9s
created: '2022-02-02T11:10:11.308Z'
modified: '2023-04-11T20:18:36.288Z'
---

# k9s

> terminal based ui to interact with your kubernetes clusters

## install

```sh
brew install derailed/k9s/k9s
```

## option

```sh
```

## usage

```sh
k9s help                  # list all available options
k9s info                  # get info about k9s runtime (logs, configs, etc..)
k9s -n mycoolns           # run k9s in a given namespace
k9s -c pod                # run k9s and launch in pod view via the pod command
k9s --context coolCtx     # start k9s in a non default KubeConfig context
k9s --readonly            # start k9s in readonly mode - with all modification commands disabled
```

## key bindings

```sh
        ? 	      # show active keyboard mnemonics and help
:alias, ctrl-a 	  # show all available aliases and resources on the cluster
:q,     ctrl-c 	  # to bail out of K9s
:po, :pod         # view k8s resource using singular/plarl shortname

/filter⏎ 	        # Filter out a resource view given a filter 	
                  # Regex2 supported ie fred|blee to filter resources named fred or blee

/! filter⏎ 	      # Inverse regex filer
                  # Keep everything that doesn’t match. Not implemented for logs

ctrl-d 	          # To delete a resource (TAB and ENTER to confirm)
ctrl-k 	          # To kill a resource (no confirmation dialog!)
ctrl-w 	          # Toggle Wide Columns 	sames as kubectl ... -o wide
ctrl-z 	          # Toggle Error State View resources in error condition

:pulse, :pu       # pluses view
:xray RESOURCE    # xray view, RESOURCE: po, svc, dp, rs..
:popeye, :po      # popeye view
```

## see also

- [[kubectl]]
- [[k0s]]
- [[k3s]]
- [k9scli.io/](https://k9scli.io/)
