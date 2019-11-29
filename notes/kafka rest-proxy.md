---
title: kafka rest-proxy
created: '2019-10-02T08:00:18.210Z'
modified: '2019-11-29T10:44:27.352Z'
---

# kafka rest-proxy

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
- [[kafka schema-registry]]
