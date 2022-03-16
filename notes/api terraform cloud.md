---
tags: [iac]
title: api terraform cloud
created: '2020-10-23T09:08:16.323Z'
modified: '2022-02-01T14:42:45.238Z'
---

# api terraform cloud

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
- [[curl]]
