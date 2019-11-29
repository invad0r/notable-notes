---
tags: [go/tooling]
title: go env
created: '2019-08-21T14:55:04.431Z'
modified: '2019-08-28T08:52:51.772Z'
---

# go env

> env prints go environment information.

```sh
go env            # show current env vars go uses
      
go env GOCACHE    # print specific value


go env -json      # print in json format

```
## envoronment variables
```sh
$GOROOT     # "/usr/local/opt/go/libexec"
$GOTOOLDIR  # /usr/local/opt/go/libexec/pkg/tool/darwin_amd64"

$GOPATH     # go-workspace and places to look for code/packages; 
            # must be set to `go get`, `go build` and `go install`

$GOBIN

$PKG_CONFIG     # pkg-config

$GOCACHE        # /path/Caches/go-build"
$GOTMPDIR # 


$GOARCH       # amd64
$GOOS         # darwin

$GOHOSTARCH   # amd64
$GOHOSTOS     # darwin

$GOEXE  # 
$GOFLAGS  # 
$GOPROXY  # 
$GORACE # 
$GCCGO  # gccgo"

$CC     #clang"

$CXX    #clang++"

$CGO_ENABLED    
$GOMOD   
$CGO_CFLAGS     
$CGO_CPPFLAGS     
$CGO_CXXFLAGS     
$CGO_FFLAGS     
$CGO_LDFLAGS    
$GOGCCFLAGS 
```

## see also
- 
