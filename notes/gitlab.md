---
tags: [curl]
title: gitlab
created: '2019-07-30T06:19:49.064Z'
modified: '2019-08-20T09:45:17.042Z'
---

# gitlab

[GitLab API | GitLab](https://docs.gitlab.com/ee/api/README.html#basic-usage)

```sh
curl -L --url 'http://git.domain.net/api/v4/projects/?private_token=PR!V4T3_T0K3N&per_page=2&page=1'
```

## pagination
```sh
# use -I / --head to see:

# X-Total 	      The total number of items
# X-Total-Pages 	The total number of pages
# X-Per-Page 	    The number of items per page
# X-Page 	        The index of the current page (starting at 1)
# X-Next-Page 	  The index of the next page
# X-Prev-Page   	The index of the previous page
```

```sh
curl \
  --head \
  --header 'private-token: PR!V4T3_T0K3N' \
  --request GET \
  --url http://git.domain.net/api/v3/projects/all?page=1&per_page=100

curl \
  --request PUT \
  --header "PRIVATE-TOKEN: PR!V4T3_T0K3N" 
  --url 'https://gitlab.example.com/api/v4/namespaces?per_page=50'

curl \
  --head \
  --header "PRIVATE-TOKEN: 1234" \
  --url 'https://gitlab.example.com/api/v4/projects/8/issues/8/notes?per_page=3&page=2'
```
 
```sh 
# printf "%q" "${pages}"
# $'15\r'
pages=$(
  curl \
    --silent \
    --head   \
    --header 'private-token: PR!V4T3_T0K3N'   \
    --request GET   \
    --url 'http://git.domain.net/api/v3/projects/all' | grep 'X-Total-Pages' | awk '{print $2}'
)

pages="${pages%%[[:cntrl:]]}"  # remove carriage-return symbol \r

for((p=0; p<$pages; p++)); do \
  curl \
    --silent \
    --header 'private-token: PR!V4T3_T0K3N' \
    --request GET \
    --url "http://git.domain.net/api/v3/projects/all?page=$p" \
      | jq '.[].id';
done >> gitlab-project-id
```
[Remove "\r" from echoing out in bash script - Super User](https://superuser.com/a/1215968)

```sh
cat gitlab-project-id | while read; do
  curl \
    --silent \
    --header 'private-token: PR!V4T3_T0K3N' \
    --request GET \
    --url "http://git.domain.net/api/v3/projects/$REPLY" \
      | jq -M --raw-output '.ssh_url_to_repo'
done | tee -a gitlab-ssh-url
 #     | jq '.path_with_namespace, .description, .ssh_url_to_repo'
```

```sh
curl --request GET   --url http://git.domain.net/api/v3/projects/all?per_page=-1   --header 'private-token: PR!V4T3_T0K3N'

http POST $GITLAB_API_HOST/oauth/token grant_type=password username=$GITLAB_USERNAME password=$GITLAB_PASSWORD

pages="$(
  curl \
    --silent \
    --head \
    --header 'private-token: PR!V4T3_T0K3N' \
    --request GET \
    --url 'http://git.domain.net/api/v3/projects/all' | grep 'X-Total-Pages' | awk '{print $2}')"; do

pages=15;
for((p=0; p<$pages; p++)); do
  echo curl \
    --silent --head --header 'private-token: PR!V4T3_T0K3N' --request GET --url "http://git.domain.net/api/v3/projects/all?page=$p&per_page=100";
done
```

## runners
```sh
curl --header "PRIVATE-TOKEN: PR!V4T3_T0K3N" "https://git.domain.net/api/v4/runners"

curl \
  --silent \
  --header "PRIVATE-TOKEN: PR!V4T3_T0K3N" \
  --url "http://git.domain.net/api/v4/runners/all?status=active" | jq

curl \
  --silent \
  --header "PRIVATE-TOKEN: PR!V4T3_T0K3N" \
  --url "http://git.domain.net/api/v4/runners/161" | jq

curl \
  --silent \
  --header "PRIVATE-TOKEN: PR!V4T3_T0K3N"\
  --request DELETE \
  --url "https://gitlab.example.com/api/v4/runners/161"  
  
curl --request DELETE --header "PRIVATE-TOKEN: 9koXpg98eAheJpvBs5tK" "https://gitlab.example.com/api/v4/runners/6"
```

### get projects with a schedule
```sh
for pages in $(
  curl \
    --head \
    --silent \
    --header "PRIVATE-TOKEN: PR!V4T3_T0K3N" \
    --url "http://git.domain.net/api/v4/projects?simple=true&per_page=100" | awk 'BEGIN {FS=": "}/^X-Total-Pages/{print $2}'
  ); do
  for id in $( curl --silent --header "PRIVATE-TOKEN: PR!V4T3_T0K3N" --url "http://git.domain.net/api/v4/projects?simple=true&per_page=100&page=${page}" | jq '.[].id';); do
    curl --no-buffer --silent --header "PRIVATE-TOKEN: PR!V4T3_T0K3N" --url "http://git.domain.net/api/v4/projects/${id}" | jq '.name'
    curl --no-buffer --silent --header "PRIVATE-TOKEN: PR!V4T3_T0K3N" --url "http://git.domain.net/api/v4/projects/${id}/pipeline_schedules" | jq '.'
  done
done
```
