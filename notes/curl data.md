---
tags: [curl, heredoc, linux, network]
title: curl data
created: '2019-08-02T11:59:22.744Z'
modified: '2020-01-16T08:16:12.354Z'
---

# curl data 

## usage
```sh
 -d @myfile.json     # data from file

# heredoc
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

## see also
- [[curl]]
