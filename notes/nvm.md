---
tags: [javascript, versionmanager]
title: nvm
created: '2019-08-20T09:04:00.908Z'
modified: '2023-05-16T08:21:11.314Z'
---

# nvm

> `node version manager` - POSIX-compliant bash script to manage multiple active [[node]] versions 

## install

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
```

## option

```sh
```

## usage

```sh
nvm ls-remote                   # available versions

nvm install --lts               # downloads latest LTS version
nvm install node                # "node" is an alias for the latest version
nvm install 6.14.4              # or 10.10.0, 8.9.1, etc
nvm install-latest-npm

nvm alias                       # list aliases
nvm alias default 18.14         # set default node version in shell

nvm use node
nvm use 5.12.0                  # used older version not having class

nvm run node --version

nvm exec 4.2 node --version     # run any arbitrary command in a subshell with the desired version of node

nvm which 5.0                   # get the path to the executable to where it was installed:
```

## see also

- [[node]], [[npm]], [[nxm]]
- [[sdk]]
- [[rvm]]
- [[asdf]]
- [node.green](https://node.green/) table of features shipped per node version
