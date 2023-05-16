---
tags: [go]
title: go datastructures
created: '2019-07-30T06:19:49.068Z'
modified: '2023-05-10T12:14:55.554Z'
---

# go datastructures


## enum

> user definded type consisting of set of name constants called `enumerators`

```go
enum rainbowColors {
  red    = 1
  orange = 2
  ..
}

const (                     // results in:
  StatusOpen Status = iota  // StatusOpen    = 0
  StatusClose               // StatusClosed  = 1
  StatusUnkown              // StatusUnknown = 2
)
```

[[ruby symbol]]

## slice

```go
// slicing an array
s[m:n]                       // 0 ≥ m ≥ n ≥ len(s), elements m thorugh n-1

os.Args[1:len(os.Args)]     // if "m" || "n" is ommited it defaults to 0 or len(s)
os.Args[1:]                 // abrev. for:


// initialize
// slice implements a `growth stategy` - is no space is available a new array is created and the items are copied over
var bars []Bar
bars := make([]Bar, 0)


bars := make([]Bar, len(foo))  // predfined length

bars := make([]Bar, 0, len(foo)) //init with 0-length and predefine capacity
```

## maps

```go
val a m[string]string

b := map[string]string        // initializes values

c := make(map[string]string)  // initializses capasity

// initalize
make ( map[string]int )
//        └───┬──┘
//   must be comparable wiht `==`
```


## struct

> a struct is a typed collection of fields, usefull for grouping data into records

```go
// initializing structs
type Student struct {
  Name string
  Age  int
}
var a Student           // a == Student{"", 0}
a.Name = "Alice"        // a == Student{"Alice", 0}


//`new` keyword returns pointer to newly created struct
var pa *Student         // pa == nil
pa      = new(Student)  // pa == &Student{"",0} 
pa.Name = "Alice"       // pa == &Student{"Alice",0} 


// You can also create and initialize a struct with a `struct literal`
b := Student{           // b == Student{"Bob", 0}
  Name: "Bob",
}

pb := &Student {        // pb == &Student{"Bob", 8}
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

- [Create, initialize and compare structs · YourBasic Go](https://yourbasic.org/golang/structs-explained/)

## see also

- [[go]]
