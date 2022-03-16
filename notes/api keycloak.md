---
tags: [api]
title: api keycloak
created: '2020-01-20T19:49:21.872Z'
modified: '2022-03-16T05:42:14.928Z'
---

# api keycloak

## usage

```sh
GET /auth/admin/{realm}/users/count
curl -s -X GET \
  -H "Accept: application/json" -H "Authorization: Bearer $TOKEN" \
  http://KEYCLOAK/auth/admin/realms/master/users/count

GET /auth/admin/realms/master/users
curl -s -X GET \
  -H "Accept: application/json" -H "Authorization: Bearer $TOKEN" \
  http://KEYCLOAK/auth/admin/realms/master/users


GET /auth/admin/realms
curl -s -X GET \
  -H "Accept: application/json" -H "Authorization: Bearer $TOKEN" \
  http://KEYCLOAK/auth/admin/realms | jq '.[].realm'

curl -s -X GET \
  -H "Accept: application/json" -H "Authorization: Bearer $TOKEN" \
  http://KEYCLOAK/auth/admin/realm/REALM
REALM


# GET /{realm}/users/{id}
curl -s -X GET \
  -H "Accept: application/json" -H "Authorization: Bearer $TOKEN" \
  http://KEYCLOAK/auth/admin/realms/master/users/5b1778a6-dd11-4321-9ab5-e90396c1e47b


GET /admin/realms/{realm}/clients/{id}/client-secret
GET /{realm}/clients


# admin token
curl -s -X POST -H "Content-Type: application/x-www-form-urlencoded" \
    "http://KEYCLOAK/auth/realms/master/protocol/openid-connect/token" \
    -d "username=USER" -d "password=PASS" -d 'grant_type=password' -d 'client_id=admin-cli' \
    | jq -r '.access_token'

# client token
curl -ss -X POST -H 'Content-Type: application/x-www-form-urlencoded' \
  http://KEYCLOAK/auth/realms/REALM/protocol/openid-connect/token \
  -d 'client_id=CLIENT_ID&client_secret=CLIENT_SECRET&grant_type=client_credentials' \
  | jq -r '.access_token'

curl -H "Authorization: bearer $TOKEN" http://API/customers/1
```

## see also

- [[kcadm.sh]]
- [how-to-get-client-secret-via-keycloak-api](https://stackoverflow.com/questions/53538100/how-to-get-client-secret-via-keycloak-api/53825640)
- [[nexus api]]
- [[graylog api]]
- [[gitlab api]]
