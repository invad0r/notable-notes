---
title: kafka schema-registry api
created: '2019-10-02T08:00:24.539Z'
modified: '2020-02-14T11:28:03.526Z'
---

# kafka schema-registry api

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
- [[kafka rest-proxy api]]
