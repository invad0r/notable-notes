---
tags: [shell/bash/builtin]
title: bash fg
created: '2019-08-02T06:42:37.596Z'
modified: '2022-04-27T14:22:29.052Z'
---

# bash fg

> move job to the foreground

## usage

```sh
%N          # job number [N]
%S          # invocation of job begins with string "S"
%?S         # invocation of job contains within it string "S"
%%          # "current" job (last job stopped in foreground or started in background)
%+          # "current" job (last job stopped in foreground or started in background)
%-          # last job
$!          # last background process
```

```sh
fg           # brings a background job into the foreground
fg %+        # brings most recently invoked background job
fg %-        # brings second most recently invoked background job
fg %N        # brings job number N
fg %string   # brings job whose command begins with string
fg %?string  # brings job whose command contains string
```

## see also

- [[bash jobs]]
- [[bash bg]]
- [[bash process-handling]]
- [[bash waits]]
