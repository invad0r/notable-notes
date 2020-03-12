---
title: nexus api
created: '2019-11-05T08:23:35.188Z'
modified: '2020-02-28T22:03:41.652Z'
---

# nexus api

## usage
```sh
# getting auth token for npm
curl -s -X PUT \
  -H "Accept: application/json" -H "Content-Type:application/json" \
  --data '{"name": "'${NPM_USER}'", "password": "'${NPM_PASS}'"}' \
  http://$NPM_URL-/user/org.couchdb.user:${NPM_USER} \
  | jq -r '.token'
```

## see also
- [[graylog api]]
- [[npm]]
