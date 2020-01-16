---
tags: [bash/built-in]
title: bash fg
created: '2019-08-02T06:42:37.596Z'
modified: '2020-01-15T07:21:17.907Z'
---

# bash fg

```sh
fg           # brings a background job into the foreground
fg %+        # brings most recently invoked background job
fg %-        # brings second most recently invoked background job
fg %N        # brings job number N
fg %string   # brings job whose command begins with string
fg %?string  # brings job whose command contains string
```

| Notation | Meaning        |
|--        |--              |
| `%N`     | Job number [N] |
| `%S`     | Invocation (command-line) of job begins with string S                   |
| `%?S`    | Invocation (command-line) of job contains within it string S            |
| `%%`     | "current" job (last job stopped in foreground or started in background) |
| `%+`     | "current" job (last job stopped in foreground or started in background) |
| `%-`     | Last job                 |
| `$!`     | Last background process  |


## see also
- [[bash jobs]]
- [[bash bg]]
- [[bash process-handling]]
- [[bash waits]]
