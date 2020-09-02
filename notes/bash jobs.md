---
tags: [bash/built-in]
title: bash jobs
created: '2019-08-02T06:42:37.604Z'
modified: '2020-08-25T14:56:23.479Z'
---

# bash jobs

> lists the jobs running in the background, giving the job number

## usage
```sh
#  JOBSPEC
#  Notation  Meaning        
#  `%N`      Job number [N] 
#  `%S`      Invocation (command-line) of job begins with string S                   
#  `%?S`     Invocation (command-line) of job contains within it string S            
#  `%%`      "current" job (last job stopped in foreground or started in background) 
#  `%+`      "current" job (last job stopped in foreground or started in background) 
#  `%-`      Last job                 
#  `$!`      Last background process  

jobs         # lists all jobs (use with -l to see associated PID)
```
## see also
- [[bash kill]]
- [[bash process-handling]]
- [[bash fg]]
- [[bash bg]]
- [[bash wait]]
