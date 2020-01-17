---
title: capabilities
created: '2020-01-17T07:20:37.598Z'
modified: '2020-01-17T07:38:35.959Z'
---

# capabilities

> capabilities are properties of processes

### Traditionally there are three sets:
- Permitted capabilities `p`: capabilities that may be "activated" in the current process.
- Effective capabilities `e`: capabilities that are currently usable in the current process.
- Inheritable capabilities `i`: file capabilities that may be inherited.


### categories of processes: 
- privileged processes: effective user ID is 0, referred to as `superuser` or `root`
- unprivileged processes: effective UID is nonzero

Privileged processes bypass all kernel permission checks
unprivileged processes are subject to full permission checking based on the process's credentials (usually: effective UID, effective GID, and supplementary group list)

## capabilities list
```sh
CAP_IPC_LOCK  # lock memory
```
## see also
- [[capsh]]
- [[getcap]]
