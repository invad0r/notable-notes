---
title: terraform cloud api
created: '2020-10-23T09:08:16.323Z'
modified: '2020-10-23T12:37:37.868Z'
---

# terraform cloud api

## usage
```sh
curl -s --request GET \
  --header "Authorization: Bearer TOKEN"   \
  --header "Content-Type: application/vnd.api+json" \
  "https://app.terraform.io/api/v2/organizations/ORGANIZATION/oauth-clients"

GET /oauth-clients/:oauth_client_id/oauth-tokens

GET /workspaces/:workspace_id/vars
```
## see also
- [[terraform]]
