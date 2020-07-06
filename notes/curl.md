---
pinned: true
tags: [curl, linux, network]
title: curl
created: '2019-07-30T06:19:49.032Z'
modified: '2020-07-06T13:34:25.739Z'
---

# curl

## usage
```sh
curl -O url                     # write output to a file named
curl -o filename url            # write output to a file named filename

curl -L githuburl               # redo the request on the new place/redirect
curl -s url	                    # --silent

select HOST in ifconfig.me icanhazip.com ipecho.net/plain ipinfo.io/ip; do
  curl $HOST; echo; break;      # get public ip
done

curl --data "param1=value1&param2=value2" http://hostname/resource

curl --form "fileupload=@filename.txt" http://hostname/resource

curl -XPOST -d @filename http://hostname/resource

# proxy - resolve for not editing hosts
curl --proxy "" \
  --include \
  --resolve foo.bar:443:192.200.168.85 \
  https://foo.bar/3ab655

curl --url "http://www.example.com?$(date +%s)"                     # cache breaker
curl -H 'Cache-Control: no-cache' --url "http://www.example.com"    # cache

curl -H 'Host: foo.com' 1.2.3.4

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
