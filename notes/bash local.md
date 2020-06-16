---
tags: [bash/built-in]
title: bash local
created: '2019-08-02T06:42:37.608Z'
modified: '2020-05-05T06:53:35.125Z'
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
- [[bash function]]
- [[bash return]]
