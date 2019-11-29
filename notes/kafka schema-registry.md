---
title: kafka schema-registry
created: '2019-10-02T08:00:24.539Z'
modified: '2019-11-29T10:44:56.373Z'
---

# kafka schema-registry

## usage
```sh
curl -s -X GET \
  --cacert ./ca_chain.pem --key ./key.pem --cert ./cert.pem \
  "https://HOST:8081/subjects" | jq


curl -s -X GET \
  --cacert ./ca_chain.pem --key ./key.pem --cert ./cert.pem \
  "https://HOST:8081/subjects/foo.bar.avro.command.CreateCustomer/versions" | jq

curl -s -X GET \
  --cacert ./ca_chain.pem --key ./key.pem --cert ./cert.pem \
  "https://HOST:8081/subjects/foo.bar.avro.command.CreateCustomer/versions/1" | jq
```

## see also
- [[kafka]]
- [[kafka rest-proxy]]
