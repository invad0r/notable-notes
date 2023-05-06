---
tags: [shell/bash/builtin]
title: bash pushd
created: '2019-08-02T06:42:37.617Z'
modified: '2023-04-12T11:52:47.224Z'
---

# bash pushd

> add/remove directories to/from stack

## usage

```sh
pushd /opt/path/logs    # switch to path and put on the stack

pushd +2                # bring the 3rd directory on the stack to the front (0-based) and rotating the stack


pushd $(mktemp -d)

popd
```

## see also

- [[bash dirs]]
- [[mktemp]]
- [[z]]
- [[bash fd]]
