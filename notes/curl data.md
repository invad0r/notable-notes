---
tags: [bash, curl, heredoc, network]
title: curl data
created: '2019-08-02T11:59:22.744Z'
modified: '2019-08-05T19:52:28.136Z'
---

# curl data 

## heredoc
```sh
curl -0 -v -XPOST \
  http://www.example.com/api/users \
  -d @- << EOF
{
    "field1": "test"
}
EOF
 
echo curl -XPOST   \
  --url 'http://alertmanager.service.dstage.domain.net:9093/api/v1/alerts'   \
  --data @<(cat << EOF
[
  $(
    curl -XGET \
      --silent \
      --url 'http://alertmanager.service.dstage.domain.net:9093/api/v1/alerts' \
      | jq -c '.data[]|select(.labels.alertname=="PressportalBackendExecutionError")| .status = "resolved"'
  )
]
EOF
)
```
## data from file
```sh
-d @myfile.json
```

