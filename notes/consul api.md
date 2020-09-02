---
tags: [curl, iac]
title: consul api
created: '2019-07-30T06:19:49.077Z'
modified: '2020-08-21T07:08:56.729Z'
---

# consul api

> api can perform basic CRUD operations on nodes, services, checks, configuration etc.

## usage
```sh
GET /v1/status/leader

# /agent endpoint used to interact with local consul-agent !
GET	/v1/agent/members

PUT	/v1/agent/service/register    # add new service to local agent


# /catalog endpoint register/deregister nodes, services, and checks in Consul
GET /v1/catalog/services

GET /v1/catalog/services | jq -r 'to_entries[].key'         # get only service names

GET /v1/catalog/service/SERVICE_NAME | jq -r '.[] | "\(.Node) \(.ServicePort) \(.ServiceID)"'

GET /v1/catalog/service/SERVICENAME | jq '.[].ServiceID'    # get service id

GET /v1/catalog/register

PUT /v1/catalog/register
{ 
  "Datacenter": "dc1", 
  "Node": "NODE", 
  "Address": "1.2.3.4", 
  "ServiceName": "SERVICE_NAME" 
}

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
