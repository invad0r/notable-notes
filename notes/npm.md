---
tags: [lang/javascript]
title: npm
created: '2019-07-30T06:19:49.182Z'
modified: '2019-08-02T07:27:33.030Z'
---

# npm

`node package manager`

### .npmrc
```sh
registry=https://nexus.domain.net/repository/npm-internal/
_auth=AUTH
strict-ssl=false
```

### registry
```sh
npm --registry https://nexus.domain.net/repository/npm-all/ install gulp-coffee
```
[Configuring Your .npmrc for an Optimal Node.js Environment](https://nodesource.com/blog/configuring-your-npmrc-for-an-optimal-node-js-environment)


## get
```sh
npm get   # list configs and paths
```


## setting auth token
```sh
echo "getting token .."
export TOKEN=$(
  curl -s -X PUT \
    -H "Accept: application/json" \
    -H "Content-Type:application/json" \
    --data '{"name": "'${NPM_USER}'", "password": "'${NPM_PASS}'"}' \
    http://$NPM_URL-/user/org.couchdb.user:${NPM_USER} \
    | jq -r '.token'
)

echo "setting registry .."
npm set registry "http://$NPM_URL"

echo "setting token .."
npm set //$NPM_URL:_authToken $TOKEN
```
