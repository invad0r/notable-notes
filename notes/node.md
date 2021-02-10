---
tags: [javascript]
title: node
created: '2020-02-28T21:20:20.353Z'
modified: '2021-02-08T11:11:29.218Z'
---

# node

## install
`brew install node`

## usage
```sh
# environment variables
NODE_OPTIONS=--max-old-space-size=32768

# flags
# -c, --check   check syntax without executing, exits with error code if script is invalid
# -e, --eval    string Evaluate string as JavaScript.


node --version              # get version

node                        # starts repl

node -e "console.log(1)"    # evaluate string

node -e "var data = require('./FILE'); console.log(JSON.stringify(data, null, 2));" # pretty print json from js-obj
```
## repl
```js
process.cwd()       // current working directory of the nodejs process

process.env         // print env variables

process.version     // current nodejs version


var data = require('./FILE')   // load a FILE
```
## see also
- [[javascript]]
- [[npm]]
- [nodejs.org/api/process.html](https://nodejs.org/api/process.html)
