---
tags: [api]
title: kafka rest-proxy api
created: '2019-10-02T08:00:18.210Z'
modified: '2020-09-02T17:29:03.845Z'
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
