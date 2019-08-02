---
tags: [lang/go]
title: go cli tooling
created: '2019-07-30T06:19:49.064Z'
modified: '2019-07-30T08:02:09.507Z'
---

# go cli tooling

```sh
go help

go build

go install

go test

go run <FILE>
```
```sh
go env    # show current env vars go uses

          # GOPATH  - go-workspace and places to look for Go code/packages
          #           must be set to get, build and install packges !!
          # GOROOT  - only 
          
go env GOCACHE
```

### go get

> `go get` downloads the packages named by the import paths, along with their dependencies.
> Then installs the package, using `go install`, which uses go build and go build caches recent build results in `$GOPATH/pkg`

[go get - Does go get command do cache? - Stack Overflow](https://stackoverflow.com/a/52813009/2087704)

```sh
go get -v github.com/yada/yad   # verbose

    -v
    -u  # update ?!

go get ./...    # install all dependencies of project recursively 
```
