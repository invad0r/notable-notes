---
tags: [go]
title: go
created: '2019-07-30T06:19:49.075Z'
modified: '2022-01-17T13:30:05.257Z'
---

# go

> `go` is a tool for managing go source code


```
  has                             doesn't have

+ package system                - implicit numeric conversion
+ first-class-functions         - constructors/destructors
+ lexical-scope                 - operator overloading
+ system call interface         - default parameter values
+ immutable string in utf-8     - inheritance (type-based inheritance → subclasses)
+ struct ~ class                - generics    `parametrics polimorphism` ≈ `generics`
+ concurrency support (CSP)     - exceptions
                                - macros
+ `garbage collected`           - function annotations
+ it's `staticallly typed`      - thread local storage
                                - inheritance but composition of type
                                - explicit declaration, interface-implementation required
```

## install

```sh
curl -O https://dl.google.com/go/go1.13.7.linux-amd64.tar.gz
tar xvzf go1.13.7.linux-amd64.tar.gz && mv go /usr/local/

export GOPATH=$(go env GOPATH)
export PATH="${PATH}:/usr/local/go/bin:${GOPATH}/bin"
```

## usage

```sh
GOROOT             # /usr/local/opt/go/libexec
GOTOOLDIR          # /usr/local/opt/go/libexec/pkg/tool/darwin_amd64
GOPATH             # go-workspace and places to look for code/packages; must be set to `go get`, `go build` and `go install`
GOBIN              # -
PKG_CONFIG         # pkg-config
GOCACHE            # /path/Caches/go-build
GOTMPDIR           # -
GOARCH             # amd64
GOOS               # darwin
GOHOSTARCH         # amd64
GOHOSTOS           # darwin
GCCGO              # gccgo
CC                 # clang
CXX                # clang++
CGO_ENABLED        # -
GOMOD              # -
GO11MODULE
```

```sh
go help env     # more information about a command

go mod init invad0r/hello         # creates a new module, initializing the `go.mod` that describes it
                                  # `go build`, `go test` and other package-building commands add new dependencies to `go.mod`
go mod tidy                       # remove unused dependencies

go list -m all                        # lists the current module and all its dependencies
go list -m -versions rsc.io/sampler   # list available tagged versions of module
go list -m rsc.io/...                 # list current versions

go get                            # downloads packages named by the import paths, along dependencies, 
                                  # then installs the package, using `go install`, 
                                  # which uses `go build` and go build caches recent build results in `$GOPATH/pkg`
                                  # flags
                                  #   -v    enables verbose progress and debug output
                                  #   -u    update the named packages and their dependencies
                                  #   -d    stop after downloading the packages; don't install the packages
go get -v github.com/user/repo    # install specific package
go get rsc.io/sampler@v1.3.1      # install with specific version, defaults to `@latest`
go get ./...                      # install all dependencies of project recursively


go doc -all rsc.io/quote/v3       # get documentation

go clean -cache -modcache -i -r   # clear cache


go run

go test -json           # Convert test output to JSON suitable for automated processing


go env            # show current env vars go uses
go env GOCACHE    # print specific value
go env -json      # print in json format
```

## semicolon rule

> `;` terminates statements

if last token before new line:
- is an `identifiere`   -> `int`, `float64`
- is an `basic literal` -> `number`, `string`
- is a `token`          -> `break`, `continues`, `fallthrough`, `return`, `++`, `--`, `)`, `}`

if the new line comes after a `token` that could end the statement => insert `;`

## see also

- [[go-template]]
- [[go lang]]
- [go-install-vs-go-build/](https://pocketgophers.com/go-install-vs-go-build/)
- [Does go get command do cache?](https://stackoverflow.com/a/52813009/2087704)
- [lecstor.com/go-clear-cache](https://lecstor.com/go-clear-cache/)
- [[gcc]]
