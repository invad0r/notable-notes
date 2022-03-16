---
tags: [api]
title: api kafka schema-registry
created: '2019-10-02T08:00:24.539Z'
modified: '2022-02-01T14:46:35.370Z'
---

# api kafka schema-registry

## usage

```sh
GET /subjects

GET /subjects/foo.bar.avro.command.CreateCustomer/versions

GET /subjects/foo.bar.avro.command.CreateCustomer/versions/1

DELETE /subjects/path.account.avro.AccountEventAvro"

curl -s -X GET --cacert ./ca_chain.pem --key ./key.pem --cert ./cert.pem 
```

## see also

- [[kafka]]
- [[api kafka rest-proxy]]
