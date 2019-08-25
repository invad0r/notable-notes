---
tags: [go/tooling]
title: go env
created: '2019-08-21T14:55:04.431Z'
modified: '2019-08-21T15:30:39.499Z'
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
$GOPATH  # go-workspace and places to look for code/packages; 
         # must be set to `go get`, `go build` and `go install`

$GOARCH="amd64"

$GOBIN=""

$GOCACHE="/path/Caches/go-build"

$GOEXE=""

$GOFLAGS=""

$GOHOSTARCH="amd64"

$GOHOSTOS="darwin"

$GOOS="darwin"

$GOPROXY=""

$GORACE=""

$GOROOT="/usr/local/opt/go/libexec"

$GOTMPDIR=""

$GOTOOLDIR="/usr/local/opt/go/libexec/pkg/tool/darwin_amd64"

$GCCGO="gccgo"

$CC="clang"

$CXX="clang++"

$CGO_ENABLED="1"

$GOMOD=""

$CGO_CFLAGS="-g -O2"

$CGO_CPPFLAGS=""

$CGO_CXXFLAGS="-g -O2"

$CGO_FFLAGS="-g -O2"

$CGO_LDFLAGS="-g -O2"

$PKG_CONFIG="pkg-config"

$GOGCCFLAGS="-fPIC -m64 -pthread -fno-caret-diagnostics -Qunused-arguments -fmessage-length=0 -fdebug-prefix-map=/var/folders/$91/l0y83p6d76l2p557ywktsnrc0000hn/T/go-build002834493=/tmp/go-build -gno-record-gcc-switches -fno-common"
```
