---
tags: [shell/bash/builtin]
title: bash jobs
created: '2019-08-02T06:42:37.604Z'
modified: '2022-04-27T14:28:16.927Z'
---

# bash jobs

> lists the jobs running in the background, giving the job number

## usage

```sh
%N      # Job number [N]
%S      # Invocation (command-line) of job begins with string S
%?S     # Invocation (command-line) of job contains within it string S
%%      # "current" job (last job stopped in foreground or started in background)
%+      # "current" job (last job stopped in foreground or started in background)
%-      # Last job
$!      # Last background process
```

```sh
jobs         # lists all jobs (use with -l to see associated PID)
```

## see also

- [[bash kill]]
- [[bash process-handling]]
- [[bash fg]]
- [[bash bg]]
- [[bash wait]]
