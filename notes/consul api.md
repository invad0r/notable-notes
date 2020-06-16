---
tags: [curl, iac]
title: consul api
created: '2019-07-30T06:19:49.077Z'
modified: '2020-04-30T14:58:58.687Z'
---

# consul api

## usage
```sh
GET /v1/catalog/services

GET /v1/catalog/register

PUT /v1/catalog/register '{ "Datacenter": "dc1", "Node": "swarm-3", "Address": "10.32.23.208", "ServiceName": "swarm-b" }'

GET /v1/catalog/service/SERVICENAME | jq '.[].ServiceID'    # get service id

PUT /v1/catalog/deregister
{
  "Datacenter": "dc1", 
  "Node": "NODE", 
  "ServiceID": "NODE-vip-svc:k4dv467p..qw07xh:HOST:PORT"
}

```

## see also
- [[consul]]
- [[curl]]
