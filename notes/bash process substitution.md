---
tags: [bash]
title: bash process substitution
created: '2019-09-05T09:17:23.395Z'
modified: '2020-01-26T17:06:22.957Z'
---

# bash process substitution

> process substiution feeds the output of a process (or processes) into the stdin of another process.
> process substitution uses `/dev/fd/<n>` files to send the results of the process(es)

## usage
```sh
>(command_list)

<(command_list)


echo >(true)
/dev/fd/63

echo <(true)
/dev/fd/63
```


## see also
- [[tee]]
- [[vault]]
- [[bash redirects]]
- [[bash read]]
- [tldp.org/.../process-sub.html](http://tldp.org/LDP/abs/html/process-sub.html)
- [what-is-the-portable-posix-way-to-achieve-process-substitution](https://unix.stackexchange.com/questions/309547/what-is-the-portable-posix-way-to-achieve-process-substitution)
