---
tags: [api, go/pkg]
title: github api
created: '2020-03-16T10:57:25.227Z'
modified: '2020-09-02T17:29:03.816Z'
---

# github api

>

## usage
```sh
curl -i https://api.github.com/users/octocat/orgs

GET /orgs/octokit/repos
curl -s https://api.github.com/users/invad0r/repos?type=owner | jq -r '.[] | select(.fork == false)|.ssh_url'
```

## see also
- [developer.github.com/v3](https://developer.github.com/v3/)
- [[gitlab api]]
- [[jq]]
