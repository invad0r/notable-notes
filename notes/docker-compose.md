---
tags: [container]
title: docker-compose
created: '2019-08-28T09:08:43.657Z'
modified: '2020-01-29T15:33:00.057Z'
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

## terraform dev compose
```yml
version: '2.4'

services:
  terraform:
    build:
      context: .
      args:
        TAG: 0.12.6
    image: docker-registry/terraform:0.12.6
    tty: true
    stdin_open: true
    environment:
      TF_VAR_vsphere_server: ${vsphere_server}
      TF_VAR_vsphere_user: ${vsphere_user}
      TF_VAR_vsphere_password: ${vsphere_password}
    volumes:
    - ./:/opt/terraform/
    - /var/run/docker.sock:/var/run/docker.sock
```

## see also
- [[capabilities]]
- [[yml]]
