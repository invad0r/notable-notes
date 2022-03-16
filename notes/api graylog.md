---
tags: [curl]
title: api graylog
created: '2019-07-30T06:19:48.987Z'
modified: '2022-02-01T14:43:47.199Z'
---

# api graylog

> playing around with graylog api for migration purposes

## usage
```sh
/api/api-browser			# use http-login and set user-token

curl -X POST -H 'Content-Type: application/json' -H 'Accept: application/json' \
	-H 'X-Requested-By: cli' \
  'http://host/api/system/sessions' \
	-d '{"username":"GM", "password":"superpower", "host":""}'

curl -X GET -H 'Content-Type: application/json' -H 'Accept: application/json' \
  -H 'X-Requested-By: cli' \
  -u "1dmol1kp84...jdodu5omr5v:token" \
  "http://host"


GET /api/users/admin/tokens

POST /api/users/admin/tokens/admin '{ "name" : "icinga", "token" : "TOKEN", "last_access" : "1970-01-01T00:00:00.000Z" }'


GET /api/users | jq '.users[].username'

# index-set id
GET /api/system/indices/index_sets?skip=0&limit=0&stats=false  | jq -r '.index_sets[] | select(.title == "some-index") | .id'


GET /api/system/indexer/indices

GET /api/cluster?pretty=true

GET /api/system/indexer/indices | jq -r '.closed.indices[]' | sort

POST /api/system/indexer/indices/${index}/reopen

GET /api/system/indexer/indices/${index} | jq '.routing[].node_name, .reopened'

GET /api/system/indices/index_sets?skip=0&limit=0&stats=false | jq -r '.index_sets[] | select(.title == "mb-processing") | .id'

DELETE /api/system/indexer/indices/${index}

GET /api/streams | jq '.streams[] | .id, .title'

GET /api/streams/5b068c6d18e
```

## see also

- [[api elasticsearch]]
- [[api gitlab]]
