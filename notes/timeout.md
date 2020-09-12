---
tags: [bash]
title: timeout
created: '2020-03-26T10:21:46.452Z'
modified: '2020-09-02T17:44:26.269Z'
---

# timeout

> run a command with a time limit

## usage
```sh
timeout 2 sleep 1

timeout 12h bash -c 'until ssh root@mynewvm; do sleep 10; done'
```

## see also
- [[sleep]]
- [[bash time]]
- [[bash wait]]
- [man7.org/linux/man-pages/man1/timeout.1.html](http://man7.org/linux/man-pages/man1/timeout.1.html)
