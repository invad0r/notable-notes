---
tags: [bash, bash/builtin]
title: bash pushd
created: '2019-08-02T06:42:37.617Z'
modified: '2019-08-18T16:09:32.927Z'
---

# bash pushd
[[bash popd]]
[[bash dirs]]

```sh
pushd /opt/path/logs    # switch to path and put on the stack

pushd +2                # bring the 3rd directory on the stack to the front (0-based) and rotating the stack
```
