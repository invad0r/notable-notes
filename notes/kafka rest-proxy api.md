---
title: kafka rest-proxy api
created: '2019-10-02T08:00:18.210Z'
modified: '2020-02-14T11:29:15.671Z'
---

# kafka rest-proxy api

## usage
```sh

GET /topics

GET /topics/testTopic

GET topics/testTopic/partitions

POST /topics/testTopic '{"records":[{"value":{"foo":"bar"}}]}'

curl -XPOST \
  -H 'Content-Type: application/vnd.kafka.json.v2+json' \
  -H 'cache-control: no-cache' \
  "http://HOST:8082/topics/testTopic" \
  -d '{"records":[{"value":{"foo":"bar"}}]}'
```

## see also
- [[kafka]]
- [[kafka schema-registry api]]
