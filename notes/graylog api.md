---
tags: [curl]
title: graylog api
created: '2019-07-30T06:19:48.987Z'
modified: '2019-10-08T04:49:28.406Z'
---

# graylog api

> playing around with graylog api for migration purposes

## token
```sh
http://host/api/api-browser			# use http-login and set user-token

curl -X POST \
	-H 'Content-Type: application/json' \
	-H 'Accept: application/json' \
	-H 'X-Requested-By: cli' \
  'http://host/api/system/sessions' \
	-d '{"username":"GM", "password":"superpower", "host":""}'

curl -X GET \
  -u "1dmol1kp84...jdodu5omr5v:token" \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'X-Requested-By: cli' \
  "http://host"


GET http://host/api/users/admin/tokens

POST http://host/api/users/admin/tokens/admin

{ "name" : "icinga", "token" : "TOKEN", "last_access" : "1970-01-01T00:00:00.000Z" }
```

## user
```sh
GET /api/users | jq '.users[].username'
````

## index-set id
```sh
GET /api/system/indices/index_sets?skip=0&limit=0&stats=false"  | jq -r '.index_sets[] | select(.title == "some-index") | .id'
```

## indices
```sh
GET /api/system/indexer/indices


GET /api/cluster?pretty=true

GET /api/system/indexer/indices | jq -r '.closed.indices[]' | sort


POST /api/system/indexer/indices/${index}/reopen


GET /api/system/indexer/indices/${index} | jq '.routing[].node_name, .reopened'

GET /api/system/indices/index_sets?skip=0&limit=0&stats=false | jq -r '.index_sets[] | select(.title == "mb-processing") | .id'

DELETE /api/system/indexer/indices/${index}
```

## streams
```sh
GET /api/streams | jq '.streams[] | .id, .title'

GET /api/streams/5b068c6d18e
```

## see also
- [[elasticsearch api cat]]
