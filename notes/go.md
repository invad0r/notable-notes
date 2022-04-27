---
tags: [go]
title: go
created: '2019-07-30T06:19:49.075Z'
modified: '2022-04-07T07:19:54.056Z'
---

# go

> tool for managing `go` source code

## install

```sh
curl -O https://dl.google.com/go/go1.13.7.linux-amd64.tar.gz
tar xvzf go1.13.7.linux-amd64.tar.gz && mv go /usr/local/

export GOPATH=$(go env GOPATH)
export PATH="${PATH}:/usr/local/go/bin:${GOPATH}/bin"
```

## environment variables

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

go env            # show current env vars go uses
go env GOCACHE    # print specific value
go env -json      # print in json format

go env -w GO111MODULE=auto
```

## usage

```sh
go help env     # more information about a command

go mod init invad0r/hello         # creates a new module, initializing the `go.mod` that describes it
                                  # `go build`, `go test` and other package-building commands add new dependencies to `go.mod`
go mod tidy                       # remove unused dependencies

go list -m all                        # lists the current module and all its dependencies
go list -m -versions rsc.io/sampler   # list available tagged versions of module
go list -m rsc.io/...                 # list current versions

go doc -all rsc.io/quote/v3       # get documentation

go clean -cache -modcache -i -r   # clear cache


go run

go test -json           # Convert test output to JSON suitable for automated processing

go clean -i github.com/motemen/gore...    # remove installed package
```

### get

> downloads the packages named by import paths, along with dependencies. Then installs named packages like `go install`
> ⚠️ has been deprecated for installing binaries since `1.17`

#### flags

```sh
-d      # stop after downloading the packages; that is, to not install packages
-fix    # run fix tool on the downloaded packages before resolving dependencies or building the code
-t      # also download packages required to build the tests for the specified packages
-u      # use network to update named packages and dependencies
-f      # forces -u not to verify that each package has been checked out from the source control repository implied by its import path. useful if source is local fork
-v      # enables verbose progress and debug output
```

```sh
go get -v github.com/user/repo    # install specific package

go get rsc.io/sampler@v1.3.1      # install with specific version, defaults to `@latest`

go get ./...                      # install all dependencies of project recursively
```

## language

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
- [[wasm]]
