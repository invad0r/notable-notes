---
tags: [shell/bash/keyword]
title: bash while
created: '2019-07-30T06:19:49.024Z'
modified: '2022-06-02T12:12:32.373Z'
---

# bash while

> execute commands as long they succeed

## usage

```sh
while condition; do statements done


command | while read foo; do
  echo $foo
done


while read; do eval echo "$REPLY"; done < config.yml
```

## see also

- [[watch]]
- [[bash read]]
