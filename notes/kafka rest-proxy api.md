---
title: kafka rest-proxy api
created: '2019-10-02T08:00:18.210Z'
modified: '2020-01-20T18:27:42.654Z'
---

# kafka rest-proxy api

## usage
```sh
curl -XPOST \
  -H 'Content-Type: application/vnd.kafka.json.v2+json' \
  -H 'cache-control: no-cache' \
  "http://HOST:8082/topics/testTopic" \
  -d '{"records":[{"value":{"foo":"bar"}}]}'

curl -XGET http://HOST:8082/topics

curl -XGET http://HOST:8082/topics/testTopic

curl -s -XGET http://HOST:8082/topics/testTopic/partitions |jq
```

## see also
- [[kafka]]
- [[kafka schema-registry api]]
