---
tags: [curl, linux, network]
title: curl
created: '2019-07-30T06:19:49.032Z'
modified: '2020-05-06T06:19:10.292Z'
---

# curl

## usage
```sh
curl [ifconfig.me|icanhazip.com|ipecho.net/plain|ipinfo.io/ip]    # get public ip

curl -O url                     # write output to a file named
curl -o filename url            # write output to a file named filename
curl -L githuburl              # redo the request on the new place/redirect
curl -s url	                    # --silent

curl --data "param1=value1&param2=value2" http://hostname/resource

curl --form "fileupload=@filename.txt" http://hostname/resource

curl -XPOST -d @filename http://hostname/resource

curl --proxy "" --include --resolve foo.bar:443:192.200.168.85 https://foo.bar/3ab655     # proxy - resolve for not editing hosts

curl -H 'Cache-Control: no-cache' --url "http://www.example.com"    # cache

curl --url "http://www.example.com?$(date +%s)"                     # cache breaker

curl -sS "https://en.wikipedia.org/wiki/List_of_Olympic_medalists_in_judo?action=raw" \
  | grep -Eoi "flagIOCmedalist\|\[\[(.+)\]\]" \
  | cut -c"19-" | cut -d \] -f 1 | cut -d \| -f 2 | sort | uniq -c | sort -nr             # extracting-data-from-wikipedia


# sending data
curl -XPOST URL -d @myfile.json     # data from file

curl -0 -v -XPOST URL -d @- << EOF  # data from heredoc
{
    "field1": "test"
}
EOF
 
curl -XPOST --url URL --data @<(cat << EOF
[
  $(curl -XGET --silent --url URL | jq -c '.data[]')
]
EOF
)


# dict protocol - aliases:
curl dict://dict.org/m:curl                 # m  match and find
curl dict://dict.org/d:heisenbug:jargon     # d  define and lookup
curl dict://dict.org/find:curl

# Commands that break the URL description of the RFC (but not the DICT protocol) are
curl dict://dict.org/show:db
curl dict://dict.org/show:strat
```

## see also
- [[curl data]]
- [[curl write-out]]
- [Extracting data from Wikipedia - loige.co](http://loige.co/extracting-data-from-wikipedia-using-curl-grep-cut-and-other-bash-commands)
- [linux - Curl command without using cache - Stack Overflow](https://stackoverflow.com/questions/31653271/curl-command-without-using-cache)
- [[wget]]
