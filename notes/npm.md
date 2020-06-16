---
tags: [javascript, packagemanager]
title: npm
created: '2019-07-30T06:19:49.182Z'
modified: '2020-05-05T07:22:37.075Z'
---

# npm

> `node package manager`

## usage
```sh
npm run dev

npm get   # list configs and paths

npm --registry https://foo.bar/repository/npm-all/ install gulp-coffee

npm set registry "http://$NPM_URL"      # setting registry ..

npm set //$NPM_URL:_authToken $TOKEN    # setting token ..
```
```sh
# .npmrc
registry=https://host/repository/npm-internal/
_auth=AUTH
strict-ssl=false
```

## see also
- [[javascript]]
- [[node]]
- [[nexus api]]
- [Configuring Your .npmrc for an Optimal Node.js Environment](https://nodesource.com/blog/configuring-your-npmrc-for-an-optimal-node-js-environment)
