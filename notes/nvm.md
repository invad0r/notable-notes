---
tags: [javascript, versionmanager]
title: nvm
created: '2019-08-20T09:04:00.908Z'
modified: '2021-06-11T11:53:58.349Z'
---

# nvm

> `node version manager` - POSIX-compliant bash script to manage multiple active node.js versions 

## install
```sh
cd ~ && git clone https://github.com/nvm-sh/nvm.git .nvm
cd ~/.nvm && git checkout v0.38.0

cat <<EOT >> ~/.bashrc    
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"                      # loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"    # loads nvm bash_completion
EOT
```

## usage
```sh
nvm install node # "node" is an alias for the latest version

nvm install 6.14.4 # or 10.10.0, 8.9.1, etc

nvm ls-remote # available versions


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
