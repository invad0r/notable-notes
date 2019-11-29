---
tags: [container/docker]
title: docker node
created: '2019-09-03T12:52:54.863Z'
modified: '2019-09-03T12:53:21.044Z'
---

# docker node

## get node ip
```sh
docker node inspect $(docker node ls --format '{{.Hostname}}')| jq -r '.[].ManagerStatus.Addr'
```


## see also
- [[jq]]
