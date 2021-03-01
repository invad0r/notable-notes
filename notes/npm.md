---
tags: [javascript, packagemanager]
title: npm
created: '2019-07-30T06:19:49.182Z'
modified: '2021-02-15T09:03:54.135Z'
---

# npm

> `node package manager`

## install
`brew install node`

## usage
```sh
npm install -g http-server

npm run dev

npm get   # list configs and paths

npm ls -g  # list installed packages, globally

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
- [[yarn]]
- [[http-server]], [[fx]]
- [[nexus api]]
- [Configuring Your .npmrc for an Optimal Node.js Environment](https://nodesource.com/blog/configuring-your-npmrc-for-an-optimal-node-js-environment)


