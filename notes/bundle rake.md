---
tags: [ruby]
title: bundle rake
created: '2020-01-02T13:04:55.184Z'
modified: '2022-03-03T15:46:10.727Z'
---

# bundle rake

> make-like build utility for Ruby

## usage

```sh
bundle exec rake -T       # list rake tasks

bundle exec rake gitlab:env:info RAILS_ENV=production

bundle exec rake gitlab:backup:create RAILS_ENV=production      # /home/git/data/backups/ 

bundle exec rake gitlab:backup:restore RAILS_ENV=production

app:rake gitlab:backup:create
```

## see also

- [[ruby]]
- [[make]]
- [[gitlab-rake]]
