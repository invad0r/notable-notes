---
tags: [go]
title: chezmoi
created: '2023-05-15T15:31:24.441Z'
modified: '2023-05-15T15:34:59.978Z'
---

# chezmoi

## install

```sh
brew install chezmoi
```

## usage

```sh
chezmoi help

chezmoi init

chezmoi add ~/.bashrc

chezmoi edit ~/.bashrc

chezmoi diff

chezmoi -v apply

chezmoi cd  # open subshell to commit changes
git add . 
git commit -m "Initial commit"
exit


chezmoi init --apply https://github.com/$GITHUB_USERNAME/dotfiles.git   # setup with single command
chezmoi init --apply $GITHUB_USERNAME                                   # short: if github user and repo /dotfiles exist
```

## see also

- [[bash]], [[git]]
- [[go]]
