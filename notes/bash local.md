---
tags: [bash/built-in]
title: bash local
created: '2019-08-02T06:42:37.608Z'
modified: '2020-01-10T10:17:09.550Z'
---

# bash local

> Local variables can only be used within a function; they are visible only to the function where they are defined and its children

## usage
```sh
foo(){

  local foo="bar"
  echo "foo: $foo"
}
foo
echo "foo: $foo"
```

## see also
- [[bash function.md]]
