---
tags: [bash/keyword]
title: bash while
created: '2019-07-30T06:19:49.024Z'
modified: '2019-09-23T06:37:33.108Z'
---

# bash while

> Execute commands as long as a test succeeds.

```sh
while condition; do statements done
```

```sh
command | while read foo; do
  echo $foo
done
```

```sh
while read; do eval echo "$REPLY"; done < config.yml
```

## see also
- [[watch]]
