---
title: github api
created: '2020-11-20T23:42:32.328Z'
modified: '2020-11-20T23:44:30.074Z'
---

# github api

>

## usage
```sh
api.github.com

GET /users/ORG/orgs

GET /orgs/ORG/repos

GET /users/USER/repos?type=owner | jq -r '.[] | select(.fork == false)|.ssh_url'


curl --user "TOKEN:x-oauth-basic" "https://api.github.com/user"

curl --user "TOKEN:x-oauth-basic" "https://api.github.com/orgs/ORG/repos" | jq -r '.[].ssh_url'
```

## see also
- [developer.github.com/v3](https://developer.github.com/v3/)
- [[gitlab api]]
- [[jq]]
- [[gh]]
