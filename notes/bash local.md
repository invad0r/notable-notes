---
tags: [shell/bash/builtin]
title: bash local
created: '2019-08-02T06:42:37.608Z'
modified: '2022-04-27T14:29:32.238Z'
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
