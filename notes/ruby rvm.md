---
tags: [ruby, versionmanager]
title: ruby rvm
created: '2019-08-02T07:23:19.957Z'
modified: '2019-08-20T07:59:26.236Z'
---

# ruby rvm

`ruby version manager`

> `rvm` is a tool which allows you to install, manage, and work with multiple ruby environments from interpreters to sets of gems. 

[rvm.io](http://rvm.io/)

```sh
source ~/.rvm/bin/rvm

rvm list known       # lists installable ruby versions
rvm list rubies     # list installed rubies

rvm install 2.0.0

bash -l -c "rvm use 2.0.0"    # http://stackoverflow.com/a/30739863
```

## install

`sudo apt-get install ruby-full`

[installation apt - ruby-lang.org](https://www.ruby-lang.org/en/documentation/installation/#apt)

