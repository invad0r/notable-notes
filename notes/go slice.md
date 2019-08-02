---
tags: [lang/go]
title: go slice
created: '2019-07-30T06:19:49.073Z'
modified: '2019-07-30T08:02:09.544Z'
---

# go slice

```go
s[m:n]  // 0 ≥ m ≥ n ≥ len(s)
        // elements m thorugh n-1

// if "m" || "n" is ommited it defaults to 0 or len(s)
os.Args[1:len(os.Args)] 
// abrev. for:
os.Args[1:]
```

## initialize
> slice implements a `growth stategy` - is no space is available a new array is created and the items are copied over
```go
var bars []Bar
bars := make([]Bar, 0)


bars := make([]Bar, len(foo))  // predfined length

bars := make([]Bar, 0, len(foo)) //init with 0-length and predefine capacity
```
