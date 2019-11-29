---
tags: [bash]
title: bash process substitution
created: '2019-09-05T09:17:23.395Z'
modified: '2019-09-24T09:21:35.878Z'
---

# bash process substitution

> process substiution feeds the output of a process (or processes) into the stdin of another process.

process substitution uses `/dev/fd/<n>` files to send the results of the process(es)

```sh
>(command_list)

<(command_list)


echo >(true)
/dev/fd/63

echo <(true)
/dev/fd/63
```


## see also
- [[diff]]
- [[bash read]]
- [tldp.org/.../process-sub.html](http://tldp.org/LDP/abs/html/process-sub.html)
