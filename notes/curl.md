---
tags: [curl, linux, network]
title: curl
created: '2019-07-30T06:19:49.032Z'
modified: '2019-12-10T14:45:10.383Z'
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

### dict protocol

> aliases:
> m - match and find
> d - define and lookup

```sh
curl dict://dict.org/m:curl
curl dict://dict.org/d:heisenbug:jargon
curl dict://dict.org/d:daniel:web1913
curl dict://dict.org/find:curl

# Commands that break the URL description of the RFC (but not the DICT protocol) are

curl dict://dict.org/show:db
curl dict://dict.org/show:strat
```


## extracting from wikipedia
```sh
curl -sS "https://en.wikipedia.org/wiki/List_of_Olympic_medalists_in_judo?action=raw" \
  | grep -Eoi "flagIOCmedalist\|\[\[(.+)\]\]" \
  | cut -c"19-" | cut -d \] -f 1 | cut -d \| -f 2 | sort | uniq -c | sort -nr       # extracting-data-from-wikipedia
```

## cache

```sh
curl -H 'Cache-Control: no-cache' --url "http://www.example.com"

curl --url "http://www.example.com?$(date +%s)"
```

## see also
- [[curl data]]
- [[curl write-out]]
- [Extracting data from Wikipedia - loige.co](http://loige.co/extracting-data-from-wikipedia-using-curl-grep-cut-and-other-bash-commands)
- [linux - Curl command without using cache - Stack Overflow](https://stackoverflow.com/questions/31653271/curl-command-without-using-cache)
- [[wget]]
