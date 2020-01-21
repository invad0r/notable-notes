---
pinned: true
tags: [container]
title: docker-compose
created: '2019-08-28T09:08:43.657Z'
modified: '2020-01-20T12:41:41.067Z'
---

# docker-compose

> docker-compose is a tool for defining and running multi-container docker applications

## usage
```sh
docker-compose -f docker-compose.yml config   # render final yaml

docker-compose ps

docker-compose up -d service_name
```

## compose file version 3 reference
```yml
cap_add:
  - ALL

cap_drop:
  - NET_ADMIN
  - SYS_ADMIN
```

## compose file version 3 reference
```yml
cap_add:
  - ALL
cap_drop:
  - NET_ADMIN
  - SYS_ADMIN
```

## see also
- [docker-compose.terraform-run.yml](@attachment/docker-compose.terraform-run.yml)
- [docker-compose.go-build.yml](@attachment/docker-compose.go-build.yml)
- [[capabilities]]
- [[yml]]
