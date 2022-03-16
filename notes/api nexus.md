---
tags: [api]
title: api nexus
created: '2019-11-05T08:23:35.188Z'
modified: '2022-02-01T14:46:19.815Z'
---

# api nexus

## usage

```sh
curl -s  `# getting auth token for npm` \
  -H "Accept: application/json" \
  -H "Content-Type:application/json" \
  -X PUT --data '{"name": "USER", "password": "PWD"}' \
  "http://HOST/-/user/org.couchdb.user:USER" | jq -r '.token'
```

## see also

- [[api docker registry ]]
- [[jq]]
- [[api graylog]]
- [[npm]]
