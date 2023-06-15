---
tags: [javascript, json]
title: json
created: '2022-12-02T10:57:31.255Z'
modified: '2023-05-24T11:44:03.727Z'
---

# json

> `json` - something-generating-JSON-on-stdout

## install

```sh
npm install -g json
```

## option

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

- [[jq]], [[yq]]
- [[npm]]
- [[curl]]
- [[yaml]]
- [trentm.com/json/#EXAMPLES](http://trentm.com/json/#EXAMPLES)
- [[javascript object notation]]
- [json.org/json-en](https://www.json.org/json-en.html)
- [infoq.com/presentations/Heretical-Open-Source/](https://www.infoq.com/presentations/Heretical-Open-Source/)
