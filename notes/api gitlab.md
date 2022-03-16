---
tags: [api, curl]
title: api gitlab
created: '2019-07-30T06:19:49.064Z'
modified: '2022-02-01T14:43:16.674Z'
---

# api gitlab

## headers

```sh
X-Total 	              # the total number of items
X-Total-Pages 	        # the total number of pages
X-Per-Page 	            # the number of items per page
X-Page 	                # the index of the current page (starting at 1)
X-Next-Page 	          # the index of the next page
X-Prev-Page   	        # the index of the previous page
private-token: TOKEN    # token..
```
## usage

```sh
GET /api/v4/projects/8/issues/8/notes?per_page=3&page=2

GET /api/v4/projects/?private_token=TOKEN&per_page=2&page=1

# get projects with a schedule
GET /api/v4/projects?simple=true&per_page=100  | awk 'BEGIN {FS=": "}/^X-Total-Pages/{print $2}'

GET /api/v4/projects?simple=true&per_page=100&page=${page} | jq '.[].id'

GET /api/v4/projects/${id} | jq '.name'

GET /api/v4/projects/${id}/pipeline_schedules | jq '.'

GET /api/v4/namespaces?per_page=100 | jq '.[] | select(.kind=="group") | "\(.id) \(.path)"'     # get system namespaces

GET /groups/:id/projects

GET /api/v4/groups/26/projects | jq -r '.[].ssh_url_to_repo'      # ssh project url from namespace-id if group

GET /api/v4/runners

GET /api/v4/runners/161

GET /api/v4/runners/all?status=active

DELETE /api/v4/runners/161
```

## see also

- [[curl]]
- [[git]]
- [[github api]]
- [[gitlab-runner]]
- [GitLab API | GitLab](https://docs.gitlab.com/ee/api/README.html#basic-usage)
