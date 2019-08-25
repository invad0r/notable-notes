---
tags: [database, javascript]
title: mongodb
created: '2019-07-30T06:19:49.178Z'
modified: '2019-08-20T07:24:12.693Z'
---

# mongodb

```sh
mongo

db  # list databases

use <database>

db.test.count();
```

```js
_db.stats(1024^3)     # view size Gig
```

## edit multiple fields
```js
db.getCollection(‘executions’).update({“state”: “ERROR”},{“$set”: {“state”: “NO_ERROR”}}, {multi:true})
```

```js
db.getCollection('executions').find({'state': 'ERROR'},{state:1,_id:0}).toArray()

```


```js
var states = db.getCollection('executions').distinct('state')
states
states.length


for (var i=0; i<states.length; i++) {
    print(states[i]);
    db.getCollection('executions').count({state: states[i]})
}
```
```js
db.getCollection('executions').count({state: "EXECUTING"})
db.getCollection('executions').count({state: "PENDING"})
db.getCollection('executions').count({state: "FINISHED"})
db.getCollection('executions').count({state: "ERROR"})
```
