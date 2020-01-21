---
title: keycloak api
created: '2020-01-20T19:49:21.872Z'
modified: '2020-01-20T19:50:57.004Z'
---

# keycloak api

## usage
```sh
export TKN=$(curl -s -X POST \
    -H "Content-Type: application/x-www-form-urlencoded" \
    "http://HOST/auth/realms/master/protocol/openid-connect/token" \
    -d "username=USER" \
    -d "password=PASS" \
    -d 'grant_type=password' \
    -d 'client_id=admin-cli' | jq -r '.access_token')

echo "get users count.."
# GET /auth/admin/{realm}/users/count
curl -s -X GET \
  -H "Accept: application/json" -H "Authorization: Bearer $TKN" \
  http://HOST/auth/admin/realms/master/users/count | jq

echo "get users.."
# GET /auth/admin/realms/master/users
curl -s -X GET \
  -H "Accept: application/json" -H "Authorization: Bearer $TKN" \
  http://HOST/auth/admin/realms/master/users | jq


echo "get realms.."
# GET /auth/admin/realms
curl -s -X GET \
  -H "Accept: application/json" -H "Authorization: Bearer $TKN" \
  http://HOST/auth/admin/realms | jq '.[].realm'


# GET /auth/admin/realms
curl -s -X GET \
  -H "Accept: application/json" -H "Authorization: Bearer $TKN" \
  http://HOST/auth/admin/realm/foo | jq '.'
foo


# GET /{realm}/users/{id}
curl -s -X GET \
  -H "Accept: application/json" -H "Authorization: Bearer $TKN" \
  http://HOST/auth/admin/realms/master/users/5b1778a6-db75-4276-9ab5-e90396c1e47b | jq

```
## see also
- [[nexus api]]
- [[graylog api]]
- [[gitlab api]]

