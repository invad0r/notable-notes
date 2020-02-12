---
tags: [go/tooling]
title: go env
created: '2019-08-21T14:55:04.431Z'
modified: '2020-02-12T04:00:48.500Z'
---

# go env

> env prints go environment information.

## usage
```sh
go env            # show current env vars go uses
      
go env GOCACHE    # print specific value


go env -json      # print in json format

# envoronment variables
GOROOT            # "/usr/local/opt/go/libexec"
GOTOOLDIR         # /usr/local/opt/go/libexec/pkg/tool/darwin_amd64"
GOPATH            # go-workspace and places to look for code/packages; 
                  # must be set to `go get`, `go build` and `go install`
GOBIN             #
PKG_CONFIG        # pkg-config
GOCACHE           # /path/Caches/go-build"
GOTMPDIR          # 
GOARCH            # amd64
GOOS              # darwin
GOHOSTARCH        # amd64
GOHOSTOS          # darwin
GOEXE             # 
GOFLAGS           # 
GOPROXY           # 
GORACE            # 
GCCGO             # gccgo"
CC                # clang"
CXX               # clang++"
CGO_ENABLED    
GOMOD   
CGO_CFLAGS     
CGO_CPPFLAGS     
CGO_CXXFLAGS     
CGO_FFLAGS     
CGO_LDFLAGS    
GOGCCFLAGS 
```

## see also
- 
