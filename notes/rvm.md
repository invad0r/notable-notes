---
tags: [ruby, versionmanager]
title: rvm
created: '2019-08-02T07:23:19.957Z'
modified: '2021-06-01T13:41:46.909Z'
---

# rvm

> `ruby version manager` allows you to install, manage, and work with multiple ruby environments from interpreters to sets of gems

USE [[rbenv]] INSTEAD !

[duseev.com/articles/rbenv-vs-rvm/](https://duseev.com/articles/rbenv-vs-rvm/)

## install
[rvm.io/rvm/install](https://rvm.io/rvm/install)

## usage
```sh
rvm implode                     # removes all ruby installations it manages, everything in ~/.rvm

rvm user gemsets                # enable local gemsets

rvm list known                  # list installable ruby versions

rvm list rubies                 # list installed rubies

rvm install ruby

rvm install 2.0.0
```

## see also
- [[rbenv]]
- [[nvm]]
- [[gpg]]
