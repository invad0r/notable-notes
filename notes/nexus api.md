---
title: nexus api
created: '2019-11-05T08:23:35.188Z'
modified: '2020-08-26T11:22:22.443Z'
---

# nexus api

## usage
```sh
# getting auth token for npm
curl -s -H "Accept: application/json" -H "Content-Type:application/json" \
  -X PUT --data '{"name": "USER", "password": "PWD"}' \
  "http://HOST/-/user/org.couchdb.user:USER" | jq -r '.token'
```

## see also
- [[docker registry api]]
- [[jq]]
- [[graylog api]]
- [[npm]]
