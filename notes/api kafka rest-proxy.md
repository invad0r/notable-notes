---
tags: [api]
title: api kafka rest-proxy
created: '2019-10-02T08:00:18.210Z'
modified: '2022-02-01T14:46:28.451Z'
---

# api kafka rest-proxy

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
- [[api kafka schema-registry]]
