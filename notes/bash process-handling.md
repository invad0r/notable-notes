---
tags: [bash]
title: bash process-handling
created: '2019-07-30T06:19:49.016Z'
modified: '2019-08-01T07:17:40.346Z'
---

# bash process-handling

[Job Control Commands](http://tldp.org/LDP/abs/html/x9644.html)

### bash option enable/disabe job-control

[bash set](:note:cc0c0257-f4c9-46ff-a590-c2eff219f6fa) `set -o monitor / set -m`


## move to background

> to suspend a job, type `CTRL+Z` while it is running. You can also suspend a job with `CTRL+Y`. This is slightly different from `CTRL+Z` in that the process is only stopped when it attempts to read input from terminal. Of course, to interupt a job, type `CTRL+C`
```sh
myCommand &     # runs job in the background and prompts back the shell
```
## jobs
> Lists the jobs running in the background, giving the job number
```sh
jobs         # lists all jobs (use with -l to see associated PID)
```
## fg
```sh
fg           # brings a background job into the foreground
fg %+        # brings most recently invoked background job
fg %-        # brings second most recently invoked background job
fg %N        # brings job number N
fg %string   # brings job whose command begins with string
fg %?string  # brings job whose command contains string
```

## bg

```sh
bg                       # lists stopped or background jobs ; resume a stopped job in the background
fg                       # brings the most recent job in the foreground
fg <job>                 # brings job to the foreground
```



| Notation | Meaning        |
|--        |--              |
| `%N`     | Job number [N] |
| `%S`     | Invocation (command-line) of job begins with string S |
| `%?S`    | Invocation (command-line) of job contains within it string S |
| `%%`     | "current" job (last job stopped in foreground or started in background) |
| `%+`     | "current" job (last job stopped in foreground or started in background) |
| `%-`     | Last job                 |
| `$!`     | Last background process |


## disown
> removes the process from the list of jobs
```sh
disown [PID|JID]
```

### wait
```sh
wait                # waits until all background jobs have finished
```
