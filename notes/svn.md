---
tags: [linux, macos]
title: svn
created: '2019-07-30T06:19:49.249Z'
modified: '2023-03-25T12:22:37.542Z'
---

# svn

> `subversion`

## install

```sh
brew install subversion
```

## usage

```sh
svn log --xml https://repo/svn/general | grep author | sort -u | perl -pe 's/.*>(.*?)<.*/$1 = /'    # get author names

svn log --xml https://repo/svn/general/joomla_portalv3/com_portal | grep author | sort -u | perl -pe 's/.*>(.*?)<.*/$1 = /'
```

## see also

- [[git]]
- [[perl]]
- [[grep]]
