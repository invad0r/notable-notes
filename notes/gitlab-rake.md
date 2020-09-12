---
tags: [ruby]
title: gitlab-rake
created: '2020-01-03T14:25:36.220Z'
modified: '2020-09-02T17:48:42.752Z'
---

# gitlab-rake

## usage
```sh
gitlab-rake gitlab:check SANITIZE=true

bundle exec rake gitlab:backup:create RAILS_ENV=production

gitlab-rake gitlab:backup:restore BACKUP=TIMESTAMP_NUMBER
```
## see also
- [[gitlab-ctl]]
- [[bundle rake]]
