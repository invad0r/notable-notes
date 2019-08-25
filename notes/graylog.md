---
tags: [curl]
title: graylog
created: '2019-07-30T06:19:48.987Z'
modified: '2019-08-20T09:45:20.216Z'
---

# graylog

playing around with graylog api for migration purposes

```sh
curl http://graylog-ui.foo.bar:80/api/streams

curl \
  --user admin:admin \
  -H 'Accept: application/json' \
  -X POST \
  'http://graylog-ui.foo.bar:80/api/users/admin/tokens/admin'

{ "name" : "icinga", "token" : "TOKEN", "last_access" : "1970-01-01T00:00:00.000Z" }


curl --user admin:admin \
  -H 'Accept: application/json' \
  -X GET \
  'http://graylog-ui.foo.bar:80/api/users/admin/tokens'


http://graylog-ui.foo.bar:80/api/streams

curl \
  -X GET \
  -H 'Accept: application/json' \
  -u fdghmb3ln50fpid3q3rh:token \
  'http://graylog-ui.foo.bar:80/api/streams' | jq '.streams[] | .id, .title'

curl \
  -X GET \
  -H 'Accept: application/json' \
  -u b3lns5abc3h4r6s3q3rh:token \
  'http://graylog-ui.foo.bar:80/api/streams/5b068c6d18e' | jq
```
