---
tags: [bash, bash/builtin]
title: bash fg
created: '2019-08-02T06:42:37.596Z'
modified: '2019-08-19T14:19:02.089Z'
---

# bash fg

[[bash jobs]], [[bash bg]], [[bash process-handling]]

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

