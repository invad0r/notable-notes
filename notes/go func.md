---
tags: [go]
title: go func
created: '2019-07-30T06:19:49.067Z'
modified: '2020-09-01T13:04:13.554Z'
---

# go func

> functions in go are first-class-citizens - function types and function values can be used and passed around just like other values

### anonymous functions 
```go
fn := func() {
    fmt.Println("hello")
}
```

### closures

```go
func intSeq() func() int {
    i := 0
    return func() int {
        i++
        return i
    }
}

nextInt := intSeq()
fmt.Println(nextInt())      // 1
fmt.Println(nextInt())      // 2
fmt.Println(nextInt())      // 3

newInts := intSeq()
fmt.Println(newInts())      // 1
```

### functions parameterized by type e.g.
```go
func Print (type T) (s []T) {
  for _,v := range s {
    fmt.Println(v)
  }
}

// you could do:
Print(int)([]int{1,2,3})
Print(string)([]string{"foo","bar","baz"})
```

### function type and collection

```go
type Operator func(x float64) float64

// Map applies op to each element of a.
func Map(op Operator, a []float64) []float64 {
  res := make([]float64, len(a))
  for i, x := range a {
    res[i] = op(x)
  }
  return res
}

func main() {
  op := math.Abs
  a := []float64{1, -2}
  b := Map(op, a)
  fmt.Println(b) // [1 2]

  c := Map(func(x float64) float64 { return 10 * x }, b)
  fmt.Println(c) // [10, 20]
}
```
## see also
- [[go init]]
- [Go by Example: Closures](https://gobyexample.com/closures)
- [Function types and values - Programming.Guide](https://programming.guide/go/function-pointer-type-declaration.html)
