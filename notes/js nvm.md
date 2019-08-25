---
tags: [javascript, versionmanager]
title: js nvm
created: '2019-08-20T09:04:00.908Z'
modified: '2019-08-20T09:06:53.812Z'
---

# js nvm

> `node version manager` - POSIX-compliant bash script to manage multiple active node.js versions 


```sh
nvm install node # "node" is an alias for the latest version

nvm install 6.14.4 # or 10.10.0, 8.9.1, etc

nvm ls-remote # available versions


nvm use node

nvm run node --version

nvm exec 4.2 node --version    # run any arbitrary command in a subshell with the desired version of node

nvm which 5.0                  # get the path to the executable to where it was installed:
```
