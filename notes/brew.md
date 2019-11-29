---
tags: [brew, osx, packagemanager]
title: brew
created: '2019-07-30T06:19:49.028Z'
modified: '2019-09-23T06:40:59.458Z'
---

# brew

> package manager for macOS

## usage
```sh
brew list

brew search PACKAGE

brew update           # update brew itself
brew up               # alias for update


brew upgrade PACKAGE

brew cleanup -s       # Scrub the cache, including downloads 
  # -n, --dry-run  
  # -v, --verbose

# diagnotic
brew doctor

brew missing

brew man        # generate brew man-pages
```

## packages
```sh
brew install inetutils
  gnu-getopt
  socat
  findutils
  netcat
  ss
  pstree
  rmtrash
  mkcert
```

## install gnu-utils on OSX
```sh
brew search gnu                            # list possible installed gnu utils

brew install grep --with-default-names     # used with-default-names to avoid prefixing with "g"

export PATH=/usr/local/bin:$PATH           # in .bash_profile so mac version not used
```


## bash-completion docker
```sh
brew install bash-completion

ln -s /Applications/Docker.app/Contents/Resources/etc/docker.bash-completion /usr/local/etc/bash_completion.d/docker

ln -s /Applications/Docker.app/Contents/Resources/etc/docker-machine.bash-completion /usr/local/etc/bash_completion.d/docker-machine

ln -s /Applications/Docker.app/Contents/Resources/etc/docker-compose.bash-completion /usr/local/etc/bash_completion.d/docker-compose
```

```sh
brew tap caskroom/cask             # get cask

brew cask install google-chrome    # install

brew cask install insomnia

ls /usr/local/Caskroom             # ls installed caskes

brew cask create my-cask           # create-cask
```

## see also
- [[brew cask]]
- [[brew tap]]
- [[ln]]
- [How to install and use GNU Grep in OSX - apple.stackexchange.com](https://apple.stackexchange.com/questions/193288/how-to-install-and-use-gnu-grep-in-osx)
- [How to replace Mac OS X utilities with GNU core utilities - apple.stackexchange.com](https://apple.stackexchange.com/questions/69223/how-to-replace-mac-os-x-utilities-with-gnu-core-utilities)
- [How to use GNU sed on Mac OS X - stackoverflow.com](https://stackoverflow.com/questions/30003570/how-to-use-gnu-sed-on-mac-os-x)
- [Updating Your Shell with Homebrew - John D. Jameson](https://johndjameson.com/blog/updating-your-shell-with-homebrew/)
- [How to update bash on Mac OS X Yosemite - superuser.com](https://superuser.com/questions/857250/how-to-update-bash-on-mac-os-x-yosemite)

