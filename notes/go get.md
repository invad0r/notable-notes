---
tags: [go/tooling]
title: go get
created: '2019-08-21T14:55:24.797Z'
modified: '2020-02-12T03:58:16.292Z'
---

# go get

> `go get` downloads the packages named by the import paths, along with their dependencies.
> Then installs the package, using `go install`, which uses go build and go build caches recent build results in `$GOPATH/pkg`

## usage
```sh
# flags
# -v    enables verbose progress and debug output
# -u    update the named packages and their dependencies
# -d    stop after downloading the packages; don't install the packages

go get -v github.com/yada/yada   

go get ./...    # install all dependencies of project recursively 
```

## see also
- [Does go get command do cache? - Stack Overflow](https://stackoverflow.com/a/52813009/2087704)
