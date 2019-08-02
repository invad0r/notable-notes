---
tags: [bash, heredoc, linux/network]
title: curl
created: '2019-07-30T06:19:49.032Z'
modified: '2019-08-02T06:57:15.223Z'
---

# curl

```sh
curl -O url                     # write output to a local file named

curl -LO githuburl              # redo the request on the new place/redirect

curl -o filename url            # write output to a local file named

curl -s url	                    # --silent

curl --data "param1=value1&param2=value2" http://hostname/resource

curl --form "fileupload=@filename.txt" http://hostname/resource

curl -XPOST -d @filename http://hostname/resource
```

## data heredoc
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


## proxy - resolve for not editing hosts
```sh
curl --proxy "" --include --resolve foo.bar:443:192.200.168.85 https://foo.bar/3ab655
```

## public ip
```sh
curl ifconfig.me
curl icanhazip.com
curl ipecho.net/plain
curl ipinfo.io/ip
```

## write-out xargs
```sh
 xargs -I $ curl -s --write-out "\n %{http_code} - %{url_effective}" --output /dev/null --url $
```

## curl http_code
```sh
curl \
  --write-out "%{http_code}\n" \
  --silent \
  -H "Authorization: Beare eyJrIjoiCI6MX0=" \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  --output FOO \
  "http://grafana.service.dint.domain.net/api/search"
  
  
watch -d 'for TLD in de ch co.uk fr; do curl -s --write-out "%{http_code}\t%{url_effective}\n" --output foo https://www.domain.${TLD}; done'
```

```sh
curl \
  -w "$(date +%FT%T)    dns %{time_namelookup}    connect %{time_connect}   firstbyte %{time_starttransfer}   total %{time_total}   HTTP %{http_code}\n" \
  -o /dev/null \
  -s \
  "https://example.com"

# `%.0s {1..10}` <= the number is not printed and string stays. this is a printf-loop WOAH !
curl -s \
  -w "$(date +%FT%T)    dns %{time_namelookup}    connect %{time_connect}   firstbyte %{time_starttransfer}   total %{time_total}   HTTP %{http_code}\n" \
  --keepalive \
  -K <(printf 'url="https://example.com/"\n%.0s' {1..10000}) 2>/dev/null \
  | grep dns
```
[curl and HTTP 1.1 keepalive test traffic](http://lzone.de/blog/curl+and+HTTP+1.1+keepalive+test+traffic)
    
## curl-formatting
```sh
for i in {1..20}; do \
  # mesure-time
  curl -s -w "%{time_total}\n" -o /dev/null http://stage.domain.com; \
done  
curl -o /dev/null -s -w %{time_connect}:%{time_starttransfer}:%{time_total} $URL
```
```sh
timmelookup:        %{time_namelookup}\n
time_connect:       %{time_connect}\n
time_appconnect:    %{time_appconnect}\n
time_pretransfer:   %{time_pretransfer}\n
time_redirect:      %{time_redirect}\n
time_starttransfer: %{time_starttransfer}\n
-----------------------------------------\n
time_total:         %{time_total}\n
```

## extracting from wikipedia
```sh
curl -sS "https://en.wikipedia.org/wiki/List_of_Olympic_medalists_in_judo?action=raw" \
  | grep -Eoi "flagIOCmedalist\|\[\[(.+)\]\]" \
  | cut -c"19-" | cut -d \] -f 1 | cut -d \| -f 2 | sort | uniq -c | sort -nr       # extracting-data-from-wikipedia
```
[Extracting data from Wikipedia using curl, grep, cut and other shell commands | Loige](http://loige.co/extracting-data-from-wikipedia-using-curl-grep-cut-and-other-bash-commands)

## cache

```sh
curl -H 'Cache-Control: no-cache' --url "http://www.example.com"

curl --url "http://www.example.com?$(date +%s)"
```
[linux - Curl command without using cache - Stack Overflow](https://stackoverflow.com/questions/31653271/curl-command-without-using-cache)

