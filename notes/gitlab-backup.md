---
title: gitlab-backup
created: '2020-01-03T14:20:17.882Z'
modified: '2020-01-03T14:26:48.732Z'
---

# gitlab-backup

> gitlab backup wrapper

## usage
```sh
gitlab-backup create

gitlab-backup restore BACKUP=1578046258_2020_01_03_12.5.5

gitlab-rake gitlab:backup:restore BACKUP=TIMESTAMP_NUMBER
```

## see also
- [[gitlab-rake]]
