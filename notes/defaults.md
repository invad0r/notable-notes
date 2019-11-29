---
tags: [osx]
title: defaults
created: '2019-07-30T06:19:49.183Z'
modified: '2019-08-29T06:35:54.552Z'
---

# defaults

> access the mac osx user defaults system

```sh
defaults write com.apple.desktopservices DSDontWriteNetworkStores true    # disable .DS_Store creation

defaults write NSGlobalDomain AppleShowAllExtensions -bool true           # display file-extensions

defaults write com.apple.finder AppleShowAllFiles TRUE                    # display dot-files

killall Finder          # restart finder need to take effect
```

### keyboard
```sh
defaults write -g ApplePressAndHoldEnabled -bool false    # Disable Popup / Enable Key Repeat
defaults read NSGlobalDomain KeyRepeat          # default: 6
defaults read NSGlobalDomain InitialKeyRepeat   # default: 25

defaults write -g InitialKeyRepeat -int 10 
defaults write -g KeyRepeat -int 1

defaults delete NSGlobalDomain KeyRepeat          # revert to default
defaults delete NSGlobalDomain InitialKeyRepeat   # revert to default
```

## see also
- [How to increase keyboard key repeat rate on OS X? - Ask Different](https://apple.stackexchange.com/a/83923)
