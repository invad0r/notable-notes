---
tags: [go]
title: go enum
created: '2019-07-30T06:19:49.065Z'
modified: '2020-01-02T12:37:04.352Z'
---

# go enum

> user definded type consisting of set of name constants called `enumerators`

## usage
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

## see also
- [[ruby symbol]]
