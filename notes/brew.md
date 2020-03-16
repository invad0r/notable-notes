---
tags: [brew, macos, packagemanager]
title: brew
created: '2019-07-30T06:19:49.028Z'
modified: '2020-03-12T14:06:12.748Z'
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


# an `extension` to brew that allows management of `graphical applications`
brew cask

brew cask install CASK

brew cask install google-chrome    # install
brew cask install insomnia

brew cask create my-cask           # create-cask

ls /usr/local/Caskroom             # ls installed caskes


# adds more repos to the list of formulae that brew tracks, updates, and installs from
brew tap                     # list tapped repositories

brew tap tapname             # add tap

brew untap tapname           # remove a tap

brew tap caskroom/cask       # get cask
```

## see also
- [caskroom.github.io/search](https://caskroom.github.io/search)
- [How to install and use GNU Grep in osx](https://apple.stackexchange.com/questions/193288/how-to-install-and-use-gnu-grep-in-osx)
- [How to replace Mac OS X utilities with GNU core utilities](https://apple.stackexchange.com/questions/69223/how-to-replace-mac-os-x-utilities-with-gnu-core-utilities)
- [How to use GNU sed on Mac OS X - stackoverflow.com](https://stackoverflow.com/questions/30003570/how-to-use-gnu-sed-on-mac-os-x)
- [Updating Your Shell with Homebrew - John D. Jameson](https://johndjameson.com/blog/updating-your-shell-with-homebrew/)
- [How to update bash on Mac OS X Yosemite - superuser.com](https://superuser.com/questions/857250/how-to-update-bash-on-mac-os-x-yosemite)

