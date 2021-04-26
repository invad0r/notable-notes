---
tags: [ruby, versionmanager]
title: rvm
created: '2019-08-02T07:23:19.957Z'
modified: '2021-03-29T06:57:48.114Z'
---

# rvm

> `ruby version manager` allows you to install, manage, and work with multiple ruby environments from interpreters to sets of gems. 

## install
`sudo apt-get install ruby-full`

## usage
```sh
bash -l -c "rvm use 2.0.0"      # login shell - rvm is not a function, selecting rubies with 'rvm use ...' will not work.

source ~/.rvm/bin/rvm

rvm list known                  # lists installable ruby versions
rvm list rubies                 # list installed rubies

rvm install 2.0.0
```

## see also
- [[ruby]]
- [rvm.io](http://rvm.io/)
- [apt - ruby-lang.org](https://www.ruby-lang.org/en/documentation/installation/#apt)
- [rvm-is-not-a-function - stackoverflow](http://stackoverflow.com/a/30739863)
- [[bash]]
- [[gem]]
- [[asdf]]
