---
tags: [bash, bash/keyword]
title: bash while
created: '2019-07-30T06:19:49.024Z'
modified: '2019-08-02T08:36:41.974Z'
---

# bash while

```sh
while condition; do
  statements
done
```

```sh
command | while read foo; do
  echo $foo
done
```

```sh
while read; do eval echo "$REPLY"; done < config.yml
```
