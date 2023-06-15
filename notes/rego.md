---
tags: [container]
title: rego
created: '2021-03-16T15:14:14.515Z'
modified: '2023-05-25T16:13:04.286Z'
---

# rego

> "ray-go" - a high-level declarative language, purpose-built for expressing policies over complex hierarchical data structures
> inspired by datalog (query language). Rego extends Datalog to support structured document models such as json
> rego queries are assertions on data

## usage

```rego
pi := 3.14159                         # rule as a single expression and is defined in terms of a Scalar Value
rect := {"width": 2, "height": 4}     # rule as a s composite value


t if { x := 42; y := 41; x > y }      # use semicolon to separate expressions

t2 if {
    x := 42                           # use linebreak to separate expressions
    y := 41
    x > y
}
```

## see also

- [[opa]]
- [[kubectl]]
- [[jq]]
- [[wasm]]
- [[terraform]]
- [[ghci]], [[erlang]]
- [openpolicyagent.org/docs/latest/policy-language/](https://www.openpolicyagent.org/docs/latest/policy-language/)
