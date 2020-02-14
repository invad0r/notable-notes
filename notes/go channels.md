---
tags: [go]
title: go channels
created: '2020-02-13T07:11:57.806Z'
modified: '2020-02-13T07:20:50.014Z'
---

# go channels

## guarantee of delivery
- Unbuffered is guaranteed
- Buffered not guaranteed

## state
a channel can have 3 states: `nil`, `open` or `closed`
```go
var ch chan string        // is nil-state when it is declared to its zero value

ch = nil                  // is placed in nil-state by explicilty setting to nil

ch := make(chan string)   // is open-state when using built-in function: make

close(ch)                 // closed-state, when closed using built-in function: close
```

-        | `nil`   | `open`  | `closed`
--       |--       |--       |--
send     | Blocked | Allowed | Panic
receive  | Blocked | Allowed | Allowed

## with and without data
```go
ch <- "data"    // signals with data

close(ch)       // signaling without by closing channel
```

## see also
- [ardanlabs.com/blog/the-behavior-of-channels](https://www.ardanlabs.com/blog/2017/10/the-behavior-of-channels.html)
- [[go make]]

