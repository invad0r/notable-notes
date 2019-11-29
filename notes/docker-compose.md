---
attachments: [docker-compose.go-build.yml]
tags: [container]
title: docker-compose
created: '2019-08-28T09:08:43.657Z'
modified: '2019-11-15T06:58:18.753Z'
---

# docker-compose

> docker-compose is a tool for defining and running multi-container docker applications

## usage
```sh
docker-compose -f docker-compose.yml config   # render final yaml

docker-compose ps

docker-compose up -d service_name
```

## see also
- [docker-compose.terraform-run.yml](@attachment/docker-compose.terraform-run.yml)
- [docker-compose.go-build.yml](@attachment/docker-compose.go-build.yml)
- [[yml]]
