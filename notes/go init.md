---
tags: [go]
title: go init
created: '2020-09-01T13:00:26.717Z'
modified: '2020-09-01T13:03:46.822Z'
---

# go init

> init is called after all the variable declarations in the package have evaluated their initializers, and those are evaluated only after all the imported packages have been initialized

## usage

```go
package main

var X int

func init() { X = 1 }

var x2 = 2 * X

func main() { println(x2) }   // prints 0 
```

## see also

- [golang.org/doc/effective_go.html#init](https://golang.org/doc/effective_go.html#init)
- [[go func]]
