---
tags: [osx]
title: osx defaults
created: '2019-07-30T06:19:49.183Z'
modified: '2019-08-19T14:08:53.151Z'
---

# osx defaults


```sh
defaults write com.apple.desktopservices DSDontWriteNetworkStores true    # disable .DS_Store creation


defaults write NSGlobalDomain AppleShowAllExtensions -bool true     # display file-extensions

killall Finder          # restart finder need to take effect


defaults write com.apple.finder AppleShowAllFiles TRUE              # display dot-files

killall Finder          # restart finder need to take effect
```


## keyboard
```sh
defaults write -g InitialKeyRepeat -int 10

defaults write -g KeyRepeat -int 1

defaults write -g ApplePressAndHoldEnabled -bool false
```
[How to increase keyboard key repeat rate on OS X? - Ask Different](https://apple.stackexchange.com/a/83923)

```sh
defaults read NSGlobalDomain KeyRepeat && \
defaults read NSGlobalDomain InitialKeyRepeat


# default values
# InitialKeyRepeat = 25
# KeyRepeat = 6

defaults write -g InitialKeyRepeat -int 10 && defaults write -g KeyRepeat -int 1

defaults write -g InitialKeyRepeat -int 15 && defaults write -g KeyRepeat -int 3

# Revert to default settings with:
defaults delete NSGlobalDomain KeyRepeat && \
defaults delete NSGlobalDomain InitialKeyRepeat
```
