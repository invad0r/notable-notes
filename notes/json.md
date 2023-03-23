---
tags: [javascript, json]
title: json
created: '2022-12-02T10:57:31.255Z'
modified: '2023-03-22T10:45:27.350Z'
---

# json

> `json` - something-generating-JSON-on-stdout

## install

```sh
npm install -g json
```

## flags

```sh
-f FILE           # specify input FILE instead of STDIN
-I, --in-place    # edit FILE given with -f FILE in-place
-i                # shortcut for -o inspect
-H                # drop any http header block from `curl -i`
```

## usage

```sh
json OPTIONS LOOKUPS

json -I -f FILE                         # inplace format FILE
json -I -f FILE -e 'this.port=8080'     # inplace add port field

curl -is HOST | json -H forks           # drop headers
```

## see also

- [[jq]]
- [[npm]]
- [[curl]]
- [trentm.com/json/#EXAMPLES](http://trentm.com/json/#EXAMPLES)
