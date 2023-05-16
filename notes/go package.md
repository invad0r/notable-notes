---
tags: [go]
title: go package
created: '2019-07-30T06:19:49.071Z'
modified: '2023-05-10T12:10:21.620Z'
---

# go package

"[Dependency hygiene trumps code reuse](https://talks.golang.org/2012/splash.slide#28)" e.g. net package has own int-to-decimal



## fmt

```go
fmt.printf("output: %v", o)

//%v	    the value in a default format

//%+v	    add field names, when printing structs

//%#v	    a Go-syntax representation of the value

//%T	    a Go-syntax representation of the type of the value

//%%	    a literal percent sign; consumes no value
```

## see also

- [fmt - The Go Programming Language](https://golang.org/pkg/fmt/#hdr-Printing)
