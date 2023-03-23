---
tags: [packagemanager, ruby]
title: gem
created: '2019-07-30T06:19:49.225Z'
modified: '2023-03-22T08:46:59.770Z'
---

# gem

> download, install, and use ruby software packages on your system. 
> a package is called a `gem` which contains a packaged Ruby application or library.

## env

```sh
GEM_PATH                  # $HOME/.gem
GEM_HOME                  # $HOME/.gem
```

## usage

```sh
gem search ^rails

gem list                  # list installed gems

gem install drip          # install gem

gem uninstall drip        # uninstall gem
```

## see also

- [rubygems.org](https://rubygems.org/)
- [[ruby]]
- [[pip]]
