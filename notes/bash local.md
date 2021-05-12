---
tags: [shell/bash/builtin]
title: bash local
created: '2019-08-02T06:42:37.608Z'
modified: '2021-05-12T08:46:08.157Z'
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
