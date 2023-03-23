---
tags: [database]
title: mongoexport
created: '2021-09-07T07:14:32.779Z'
modified: '2023-03-22T10:44:14.352Z'
---

# mongoexport

## install

```sh
brew tap mongodb/brew && brew install mongodb-database-tools
```

## usage

```sh
mongoexport --jsonFormat=canonical --collection=COLLECTION CONNECTION_STRING

mongoimport --db=users --collection=contacts --file=contacts.json

mongoimport
```

## see also

- [[mongodump]]
- [[mongo]]
