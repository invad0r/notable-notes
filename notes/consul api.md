---
tags: [curl, iac]
title: consul api
created: '2019-07-30T06:19:49.077Z'
modified: '2020-01-28T08:47:51.670Z'
---

# consul api

## usage
```sh
GET /v1/catalog/services

GET /v1/catalog/register

PUT /v1/catalog/register '{ "Datacenter": "dc1", "Node": "swarm-3", "Address": "10.32.23.208", "ServiceName": "swarm-b" }'

GET /v1/catalog/service/SERVICENAME | jq '.[].ServiceID'    # get service id
```

## see also
- [[consul]]
- [[curl]]
