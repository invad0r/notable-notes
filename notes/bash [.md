---
tags: [bash/built-in]
title: 'bash ['
created: '2020-09-02T13:23:02.951Z'
modified: '2020-09-02T14:25:11.278Z'
---

# bash [

> evaluate conditional expression - synonym for `test`
> last argument must be a literal `]`, to match the opening `[`

## usage
```sh
[ CMD ] && CMD || CMD

[ $(echo 'ok') ] && { echo 'success'; echo 'success'; } || { echo 'fail'; echo 'fail'; }    # notic space between curly-braces

if [ CMD ]; then
fi
```
## see also
- [[bash test]]
- [[bash [ []]
- [[bash built-in vs keyword]]
