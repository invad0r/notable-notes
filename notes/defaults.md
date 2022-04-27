---
tags: [macos]
title: defaults
created: '2019-07-30T06:19:49.183Z'
modified: '2022-04-19T04:55:35.284Z'
---

# defaults

> access the mac macos user defaults system

## usage

```sh
defaults write com.apple.desktopservices DSDontWriteNetworkStores true    # disable .DS_Store creation

defaults write NSGlobalDomain AppleShowAllExtensions -bool true           # display file-extensions

defaults write com.apple.finder AppleShowAllFiles TRUE                    # display dot-files
defaults write com.apple.Finder AppleShowAllFiles true

killall Finder          # restart finder need to take effect

# keyboard
defaults write -g ApplePressAndHoldEnabled -bool false    # Disable Popup / Enable Key Repeat
defaults read NSGlobalDomain KeyRepeat          # default: 6
defaults read NSGlobalDomain InitialKeyRepeat   # default: 25
defaults write -g InitialKeyRepeat -int 10 
defaults write -g KeyRepeat -int 1
defaults delete NSGlobalDomain KeyRepeat          # revert to default
defaults delete NSGlobalDomain InitialKeyRepeat   # revert to default

# toggle display items on desktop
defaults write com.apple.finder CreateDesktop false    && killall Finder
defaults write com.apple.finder CreateDesktop true     && killall Finder


# screenshots
defaults write com.apple.screencapture location "$HOME/Pictures/screenshots"      # save to diff location
defaults write com.apple.screencapture name screenshot                            # use diff name prefix
```

## see also

- [apple.stackexchange.com/how-to-increase-keyboard-key-repeat-rate-on-os-x](https://apple.stackexchange.com/questions/10467/how-to-increase-keyboard-key-repeat-rate-on-os-x/83923#83923)
