---
tags: [javascript, packagemanager]
title: npm
created: '2019-07-30T06:19:49.182Z'
modified: '2023-05-23T07:55:34.842Z'
---

# npm

> `node package manager`

## install

```sh
brew install node
```

## .npmrc

```sh
npm help npmrc

cat <<EOF > ~/.npmrc
_auth=AUTH
registry=https://host/repository/npm-internal/
strict-ssl=false
EOF
```

## usage

```sh
npm -l             # display usage info for all commands

npm run dev

npm set registry "http://$NPM_URL"      # setting registry ..
npm set //$NPM_URL:_authToken $TOKEN    # setting token ..

npm get     # list configs and paths
```

## init - create a package.json file

```sh
-y, --yes
-f, --force
    --scope @SCOPE
-w, --workspace WORKSPACE
    --no-workspaces-update
    --include-workspace-roo
```

```sh
npm init -y
npm init PACKAGE_SPEC   # same as `npx <package-spec>
npm init @SCOPE         # same as `npx <@scope>/create`
```

## install

```sh
-S, --save, --no-save, --save-prod, --save-dev, --save-optional, --save-peer, --save-bundle
-E, --save-exact
-g, --global
    --global-style
    --legacy-bundling
    --omit OMIT             # dev, optional, peer
    --strict-peer-deps
    --no-package-lock
    --foreground-scripts
    --ignore-scripts
    --no-audit
    --no-bin-links
    --no-fund
    --dry-run
-w, --workspace WORKSPACE
    --include-workspace-root
    --install-links
```

```sh
npm --registry HOST/repository/npm-all/ install gulp-coffee
```

## ls - list installed packages

```sh
-a, --all
    --json
-l, --long
-p, --parseable
-g, --global                # list installed packages, globally
    --depth DEPTH
    --omit OMIT             # dev, optional, peer
    --link
    --package-lock-only
    --no-unicode
-w, --workspace WORKSPACE
    --include-workspace-root
    --install-links
```

```sh
npm ls PACKAGE_SPEC
npm ls -g
npm list -g
```

## config - manage the npm configuration files

```sh
    --json
-g, --global
    --editor EDITOR
-L, --location LOCATION   # locations: global, user, project
-l, --long]
```

```sh
npm config list --json

npm config set KEY=VAL
npm config get KEY
npm config delete KEY
npm config edit
```

## see also

- [[javascript]]
- [[node]]
- [[nxm]]
- [[yarn]]
- [[http-server]], [[fx]]
- [[nexus api]]
- [config .npmrc for optimal node env](https://nodesource.com/blog/configuring-your-npmrc-for-an-optimal-node-js-environment)
- [[cdk]]


