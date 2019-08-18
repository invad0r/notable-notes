---
tags: [brew, osx]
title: brew
created: '2019-07-30T06:19:49.028Z'
modified: '2019-07-30T20:38:03.376Z'
---

# brew

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

## tap
adds more repos to the list of formulae that brew tracks, updates, and installs from
```sh
brew tap                     # list tapped repositories

brew tap tapname             # add tap

brew untap tapname           # remove a tap
```

## install
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
[homebrew - How to install and use GNU Grep in OSX - Ask Different](https://apple.stackexchange.com/questions/193288/how-to-install-and-use-gnu-grep-in-osx)
[terminal - How to replace Mac OS X utilities with GNU core utilities](https://apple.stackexchange.com/questions/69223/how-to-replace-mac-os-x-utilities-with-gnu-core-utilities)
[macos - How to use GNU sed on Mac OS X - Stack Overflow](https://stackoverflow.com/questions/30003570/how-to-use-gnu-sed-on-mac-os-x)

## update bash on mac os x
[Updating Your Shell with Homebrew | John D. Jameson](https://johndjameson.com/blog/updating-your-shell-with-homebrew/)
[macos - How to update bash on Mac OS X Yosemite - Super User](https://superuser.com/questions/857250/how-to-update-bash-on-mac-os-x-yosemite)

## bash-completion docker
```sh
brew install bash-completion

ln -s /Applications/Docker.app/Contents/Resources/etc/docker.bash-completion /usr/local/etc/bash_completion.d/docker

ln -s /Applications/Docker.app/Contents/Resources/etc/docker-machine.bash-completion /usr/local/etc/bash_completion.d/docker-machine

ln -s /Applications/Docker.app/Contents/Resources/etc/docker-compose.bash-completion /usr/local/etc/bash_completion.d/docker-compose
```

## brew-cask

* an `extension` to brew that allows management of `graphical applications`
* [caskroom.github.io/search](https://caskroom.github.io/search)

```sh
brew tap caskroom/cask             # get cask

brew cask install google-chrome    # install

brew cask install insomnia

ls /usr/local/Caskroom             # ls installed caskes

brew cask create my-cask           # create-cask
```


