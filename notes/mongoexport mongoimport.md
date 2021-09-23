---
title: mongoexport mongoimport
created: '2021-09-07T07:14:32.779Z'
modified: '2021-09-07T07:25:40.527Z'
---

# mongoexport mongoimport

## install

`brew tap mongodb/brew && brew install mongodb-database-tools`

## usage

```sh
mongoexport --jsonFormat=canonical --collection=COLLECTION CONNECTION_STRING

mongoimport --db=users --collection=contacts --file=contacts.json

mongoimport
```

## see also

- [[mongodump mongorestore]]
- [[mongo]]
