---
tags: [go]
title: go enum
created: '2019-07-30T06:19:49.065Z'
modified: '2019-08-21T15:24:53.923Z'
---

# go enum
> user definded type consisting of set of name constants called `enumerators`

```go
enum rainbowColors {
  red    = 1
  orange = 2
  ..
}
```

```go

const (
  StatusOpen Status = iota
  StatusClose
  StatusUnkown
)

/*
results in:

  StatusOpen = 0
  StatusClosed = 1
  StatusUnknown = 2
*/

```
