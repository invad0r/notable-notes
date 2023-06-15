---
tags: [cloud]
title: api gitlab
created: '2023-03-11T10:08:17.544Z'
modified: '2023-05-24T08:44:54.814Z'
---

# api gitlab

## usage

```sh
curl "https://gitlab.example.com/api/v4/projects"

curl --header "Authorization: Bearer OAUTH-TOKEN" "https://gitlab.example.com/api/v4/projects"
curl --header "PRIVATE-TOKEN: <your_access_token>" "https://gitlab.example.com/api/v4/projects"
curl --header "Authorization: Bearer <your_access_token>" "https://gitlab.example.com/api/v4/projects"


GET "/api/v4/namespaces?per_page=50"

GET "/api/v4/projects?pagination=keyset&per_page=100&order_by=id&sort=asc"
```

## see also

- [[api github]]
- [[curl]]
- [[glab]]
