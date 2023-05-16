---
deleted: true
tags: [go]
title: go struct
created: '2019-07-30T06:19:49.074Z'
modified: '2023-05-10T12:10:02.209Z'
---

# go struct

> a struct is a typed collection of fields, usefull for grouping data into records

## initializing structs

```go
type Student struct {
  Name string
  Age  int
}

var a Student     // a == Student{"", 0}
a.Name = "Alice"  // a == Student{"Alice", 0}
```

> `new` keyword returns pointer to newly created struct
```go
var pa *Student         // pa == nil
pa      = new(Student)  // pa == &Student{"",0} 
pa.Name = "Alice"       // pa == &Student{"Alice",0} 
```

> You can also create and initialize a struct with a `struct literal`
```go
b := Student{  // b == Student{"Bob", 0}
  Name: "Bob",
}

pb := &Student { // pb == &Student{"Bob", 8}
  Name: "Bob",
  Age:  8,
}

c := Student{"Cecilia", 5}  // c == &Student{"Cecilia", 5}
d := Student{}              // d == &Student{"", 0}
```

## compare structs
> ompare struct values with the comparison operators `==` and `!=`
```go
d1 := Student{"David", 1}
d2 := Student{"David", 2}
fmt.Println(d1 == d2) // false
```
## see also
- [Create, initialize and compare structs · YourBasic Go](https://yourbasic.org/golang/structs-explained/)
