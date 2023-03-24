---
tags: [javascript, versionmanager]
title: nvm
created: '2019-08-20T09:04:00.908Z'
modified: '2023-03-23T07:42:03.664Z'
---

# nvm

> `node version manager` - POSIX-compliant bash script to manage multiple active [[node]] versions 

## install

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
```

## usage

```sh
nvm ls-remote           # available versions

nvm install --lts
nvm install node        # "node" is an alias for the latest version
nvm install 6.14.4      # or 10.10.0, 8.9.1, etc

nvm install-latest-npm


nvm use node

nvm run node --version

nvm exec 4.2 node --version    # run any arbitrary command in a subshell with the desired version of node

nvm which 5.0                  # get the path to the executable to where it was installed:
```

## see also

- [[node]]
- [[npm]]
- [[nxm]]
- [[asdf]]
- [[sdk]]
- [[rvm]]
- [[asdf]]
