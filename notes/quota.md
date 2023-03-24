---
tags: [linux]
title: quota
created: '2021-05-25T12:00:06.506Z'
modified: '2023-03-24T08:25:10.885Z'
---

# quota

> display disk usage and limits

## usage

```sh
quota -g      # print group quotas for the group of which the user is a member.  The optional -u flag is equivalent to the default.

quota -v      # quota will display quotas on filesystems where no storage is allocated.

quota -q      # print a more terse message, containing only information on filesystems where usage is over quota.
```

## see also

- [[ssh]]
- [[df]]
- [[du]]
