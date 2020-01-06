---
tags: [brew, osx, packagemanager]
title: brew
created: '2019-07-30T06:19:49.028Z'
modified: '2020-01-03T07:32:25.968Z'
---

# brew

> package manager for macOS

## usage
```sh
brew list


brew search PACKAGE

brew search gnu       # list possible installed gnu utils


brew update           # update brew itself
brew up               # alias for update

brew upgrade PACKAGE

brew cleanup -s       # Scrub the cache, including downloads 
                      # -n, --dry-run  
                      # -v, --verbose


brew doctor           # check your system for potential problems

brew missing          # check the given formula kegs for missing dependencies

brew man              # generate brew man-pages

brew install grep --with-default-names     # used with-default-names to avoid prefixing with "g"

brew install 
  inetutils
  gnu-getopt
  socat
  findutils
  netcat
  ss
  pstree
  rmtrash
  mkcert
  bash-completion
```

## see also
- [[brew cask]]
- [[brew tap]]
- [How to install and use GNU Grep in osx](https://apple.stackexchange.com/questions/193288/how-to-install-and-use-gnu-grep-in-osx)
- [How to replace Mac OS X utilities with GNU core utilities](https://apple.stackexchange.com/questions/69223/how-to-replace-mac-os-x-utilities-with-gnu-core-utilities)
- [How to use GNU sed on Mac OS X - stackoverflow.com](https://stackoverflow.com/questions/30003570/how-to-use-gnu-sed-on-mac-os-x)
- [Updating Your Shell with Homebrew - John D. Jameson](https://johndjameson.com/blog/updating-your-shell-with-homebrew/)
- [How to update bash on Mac OS X Yosemite - superuser.com](https://superuser.com/questions/857250/how-to-update-bash-on-mac-os-x-yosemite)

