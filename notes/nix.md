---
tags: [packagemanager]
title: nix
created: '2020-06-16T08:44:19.067Z'
modified: '2020-08-26T07:57:28.042Z'
---

# nix

> purely functional package manager 
> treats packages as values in purely functional programming languages
> packages are built by functions that don’t have side-effects and don't change after they have been built

## usage
```sh

nix-channel --update

nix-channel --add https://nixos.org/channels/nixpkgs-unstable
nix-channel --remove nixpkgs


nix-env -q                      #  list all installed packages
nix-env -qa
nix-env -qa chromium
nix-env -qas gcc                # status of the available package
nix-env -qaP | grep python3-3   # search for a particular package


nix-env -i gcc
nix-env --install gcc


nix-env -e gcc vim            # remove multiple packages
nix-collect-garbage -d        # remove unused packages

nix-env -u                    # upgrade all packages
nix-env -u vim
nix-env --upgrade vim


nix-env --rollback
```
## see also
- [[brew]]
- [[apt]]
