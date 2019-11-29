---
tags: [curl, iac]
title: consul api
created: '2019-07-30T06:19:49.077Z'
modified: '2019-11-12T07:50:04.287Z'
---

# consul api

## usage
```sh
curl \
  --write-out "\n" \
  --request PUT \
  --data '{ "Datacenter": "dc1", "Node": "swarm-3", "Address": "10.32.23.208", "ServiceName": "swarm-b" }' \
  --url 'http://host/v1/catalog/register'

GET /v1/catalog/services

GET /v1/catalog/register
```

## see also
- [[consul]]
- [[curl]]
