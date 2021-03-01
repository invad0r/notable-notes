---
title: fx
created: '2021-02-15T08:54:44.797Z'
modified: '2021-02-15T08:56:50.829Z'
---

# fx

> Function eXecution - cli json processing tool

## install
`npm install -g fx`
## usage
```sh
curl API | fx

curl ... | fx '.filter(x => x.startsWith("a"))'

echo '{"count": 0}' | fx '{...this, count: 1}'

fx commits.json | fx .[].author.name
```
## see also
- [[jq]]
- [[npm]]
- [github.com/antonmedv/fx](https://github.com/antonmedv/fx)
