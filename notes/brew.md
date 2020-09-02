---
tags: [brew, macos, packagemanager]
title: brew
created: '2019-07-30T06:19:49.028Z'
modified: '2020-08-26T11:19:02.844Z'
---

# brew

> package manager for macos

## install
`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

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
  findutils
  pstree
  rmtrash
  mkcert
  bash-completion

# cask - extension to brew allowing management of gui apps
brew cask

brew cask install CASK

brew cask install google-chrome    # install
brew cask install insomnia

brew cask create my-cask           # create-cask

ls /usr/local/Caskroom             # ls installed caskes

# tap - adds more repos to the list of formulae that brew tracks, updates, and installs from
brew tap                     # list tapped repositories

brew tap tapname             # add tap

brew untap tapname           # remove a tap

brew tap caskroom/cask       # get cask
```

## see also
- [caskroom.github.io/search](https://caskroom.github.io/search)
- [how to install and use gnu grep in macos](https://apple.stackexchange.com/questions/193288/how-to-install-and-use-gnu-grep-in-osx)
- [how to replace macos utilities with gnu core utilities](https://apple.stackexchange.com/questions/69223/how-to-replace-mac-os-x-utilities-with-gnu-core-utilities)
- [how to use gnu sed on macos](https://stackoverflow.com/questions/30003570/how-to-use-gnu-sed-on-mac-os-x)
- [Updating shell with Homebrew](https://johndjameson.com/blog/updating-your-shell-with-homebrew/)
- [how to update bash on macos](https://superuser.com/questions/857250/how-to-update-bash-on-mac-os-x-yosemite)
- [[nix]]
- [[ruby]]

