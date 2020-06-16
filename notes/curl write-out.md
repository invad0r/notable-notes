---
tags: [curl]
title: curl write-out
created: '2019-08-02T12:00:25.439Z'
modified: '2020-05-06T06:34:34.282Z'
---

# curl write-out

```sh
# write-out xargs
xargs -I $ curl -s --write-out "\n %{http_code} - %{url_effective}" --output /dev/null --url $

# url encode
curl -s -o /dev/null -w "%{url_effective}\n" --get --data-urlencode "some random" --data-urlencode "foo=bar" ""

# curl http_code
curl --write-out "%{http_code}\n" --silent -H "Authorization: Beare eyJrABCDI6MX0=" -H "Content-Type: application/json" -H "Accept: application/json" \
  --output FOO "http://foo.bar.baz/api/search"
  
  
watch -d 'for TLD in de ch co.uk fr; do curl -s --write-out "%{http_code}\t%{url_effective}\n" --output foo https://www.domain.${TLD}; done'


curl \
  -w "$(date +%FT%T)    dns %{time_namelookup}    connect %{time_connect}   firstbyte %{time_starttransfer}   total %{time_total}   HTTP %{http_code}\n" \
  -o /dev/null \
  -s \
  "https://example.com"

# `%.0s {1..10}` <= the number is not printed and string stays. this is a printf-loop WOAH !
curl -s \
  -w "$(date +%FT%T)    dns %{time_namelookup}    connect %{time_connect}   firstbyte %{time_starttransfer}   total %{time_total}   HTTP %{http_code}\n" \
  --keepalive -K <(printf 'url="https://example.com/"\n%.0s' {1..10000}) 2>/dev/null 

# mesure-time
for i in {1..20}; do 
  curl -s -w "%{time_total}\n" -o /dev/null URL; \
done  
curl -o /dev/null -s -w "%{time_connect}:%{time_starttransfer}:%{time_total}" URL
#  timmelookup:        %{time_namelookup}\n
#  time_connect:       %{time_connect}\n
#  time_appconnect:    %{time_appconnect}\n
#  time_pretransfer:   %{time_pretransfer}\n
#  time_redirect:      %{time_redirect}\n
#  time_starttransfer: %{time_starttransfer}\n
#  -----------------------------------------\n
#  time_total:         %{time_total}\n
```

## see also
[curl and HTTP 1.1 keepalive test traffic](http://lzone.de/blog/curl+and+HTTP+1.1+keepalive+test+traffic)
- [[curl]]
- [[url encoding]]
- [[xargs]]
