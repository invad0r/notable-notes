---
tags: [linux, network]
title: curl
created: '2019-07-30T06:19:49.032Z'
modified: '2021-07-08T12:57:28.350Z'
---

# curl

> `c - url` - transfer a url

## usage
```sh
-O                         # write output to a file named like original
-o filename                # write output to a file named filename
-L                         # redo the request on the new place/redirect
-s, --silent               # -
-H 'Host: foo.com'         # set Host-Header
-v, -vv, -vvv              # verbose level
--write-out
```
```sh
curl -vv telnet://127.0.0.1:7878    # send data via telnet

curl -v -XOPTIONS URL               # check for CORS - if headers Access-Control-Allow-{Headers,Methods,Origin} are present 
curl -s -H "Origin: http://localhost" -v HOST 2>&1 | grep access    # check access-* headers

curl -XGET --data "param1=val1&param2=val2" "http://HOST/resource"   # sending data via GET

curl -XGET --form "fileupload=@FILENAME" "http://HOST/resource"      # sending data via GET

curl -XPOST "URL" -d @FILENAME                                      # sending data via POST and filenamedescriptor


# data from heredoc
curl -0 -v -XPOST "URL" -d @- << EOF  
{ "field1": "test" }
EOF
 
curl -XPOST "URL" --data @<(cat << EOF
[ $(curl -XGET --silent --url URL | jq -c '.data[]') ]
EOF
)

# proxy - resolve for not editing hosts
curl --proxy "" --include --resolve HOST:PORT:ADDRESS "https://HOST/3ab655"

curl --url "http://HOST/?$(date +%s)"                    # cache breaker
curl -H 'Cache-Control: no-cache' --url "http://HOST"    # cache-control

curl -sS "https://en.wikipedia.org/wiki/List_of_Olympic_medalists_in_judo?action=raw" \
  | grep -Eoi "flagIOCmedalist\|\[\[(.+)\]\]" \
  | cut -c"19-" | cut -d \] -f 1 | cut -d \| -f 2 | sort | uniq -c | sort -nr             # extracting-data-from-wikipedia

# write-out
xargs -I $ curl -s --write-out "\n %{http_code} - %{url_effective}" --output /dev/null --url $

# url encode
curl -s -o /dev/null -w "%{url_effective}\n" --get --data-urlencode "some random" --data-urlencode "foo=bar" ""

# curl http_code
curl --silent -H "Authorization: Beare eyJrABCDI6MX0=" \
  -H "Content-Type: application/json" -H "Accept: application/json" \
  --write-out "%{http_code}\n" --output FOO \
  "http://HOST.baz/api/search"
  
  
watch -d 'for HOST in A B C; do curl -s --write-out "%{http_code}\t%{url_effective}\n" --output foo https://${HOST}; done'

curl -s -w "$(date +%FT%T)    dns %{time_namelookup}    connect %{time_connect}   firstbyte %{time_starttransfer}   total %{time_total}   HTTP %{http_code}\n" -o /dev/null "https://example.com"

# `%.0s {1..10}` <= the number is not printed and string stays. this is a printf-loop WOAH !
curl -s 
  -w "$(date +%FT%T)    dns %{time_namelookup}    connect %{time_connect}   firstbyte %{time_starttransfer}   total %{time_total}   HTTP %{http_code}\n" \
  --keepalive -K <(printf 'url="https://example.com/"\n%.0s' {1..10000}) 2>/dev/null 

# mesure-time
for i in {1..20}; do curl -s -w "%{time_total}\n" -o /dev/null URL; done  
curl -o /dev/null -s -w "%{time_connect}:%{time_starttransfer}:%{time_total}" URL
#  timmelookup:        %{time_namelookup}\n
#  time_connect:       %{time_connect}\n
#  time_appconnect:    %{time_appconnect}\n
#  time_pretransfer:   %{time_pretransfer}\n
#  time_redirect:      %{time_redirect}\n
#  time_starttransfer: %{time_starttransfer}\n
#  -----------------------------------------\n
#  time_total:         %{time_total}\n


# dict protocol - aliases:
curl dict://dict.org/m:curl                 # m  match and find
curl dict://dict.org/d:heisenbug:jargon     # d  define and lookup
curl dict://dict.org/find:curl
# Commands that break the URL description of the RFC (but not the DICT protocol) are
curl dict://dict.org/show:db
curl dict://dict.org/show:strat
```

## see also
- [[telnet]]
- [[wget]]
- [[xargs]]
- [[url encoding]]
- [curl and HTTP 1.1 keepalive test traffic](http://lzone.de/blog/curl+and+HTTP+1.1+keepalive+test+traffic)
- [loige.co/extracting-data-from-wikipedia](http://loige.co/extracting-data-from-wikipedia-using-curl-grep-cut-and-other-bash-commands)
- [curl command without using cache](https://stackoverflow.com/questions/31653271/curl-command-without-using-cache)
- [Book - Everything curl](https://ec.haxx.se/)
