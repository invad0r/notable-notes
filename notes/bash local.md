---
tags: [bash/builtin]
title: bash local
created: '2019-08-02T06:42:37.608Z'
modified: '2019-08-20T07:21:21.967Z'
---

# bash local

> Local variables can only be used within a function; they are visible only to the function where they are defined and its children.

[[bash function.md]]

```sh
foo(){

  local foo="bar"
  echo "foo: $foo"
}
foo
echo "foo: $foo"
```
