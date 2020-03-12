---
tags: [database, javascript]
title: mongo
created: '2019-07-30T06:19:49.178Z'
modified: '2020-02-28T23:02:31.382Z'
---

# mongo

> `mongo` shell is an interactive javascript interface to `mongodb` used to query and update data and perform administrative operations

## usage
```sh
mongo "mongodb://mongodb0.example.com:28015"

mongo --host=HOST --port=27017

mongo --username admin --password --authenticationDatabase admin --host HOST --port 27017

mongo --help 	            # show command line options

mongo --nodb 	            # start mongo shell without connecting to a database

mongo --shell             # used in conjunction with a javascript file (FILE.js) to continue in the mongo shell after running the FILE.js
````
```js
help                 // show help

show dbs             // show database names

show collections     // show collections in current database

show users           // show users in current database

show profile         // show most recent system.profile entries with time >= 1ms

show logs            // show the accessible logger names

show log [name]      // prints out the last segment of log in memory, 'global' is default


use DATABASE                          // select DATABASE

db                                    // list current database

db.help()                             // help on db methods

db.serverStatus().storageEngine       // get current storage engine

db.currentOp().inprog[0].msg          // progress while indexing

db.repairDatabase()                   // free up space on `mmapv1` 
db.runCommand({repairDatabase: 1})

db.stats

db.stats(1024).storageSize


db.test.count();

db.getCollection(‘executions’).update(    // edit multiple fields
  { "state": "ERROR" },
  { "$set": { "state": "NO_ERROR" } },
  { multi: true }
)                                 

db.getCollection('executions').find(
  { 'state': 'ERROR' },
  { state: 1, _id: 0 }
).toArray()

db.getCollection('COLLECTION').count({state: "EXECUTING"})    // count
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

## see also
- [[mongod]]
- [[mongodump]]
- https://docs.mongodb.com/manual/reference/mongo-shell/#command-helpers
- https://scalegrid.io/blog/understanding-managing-disk-space-on-your-mongodb-server/
- [[mysql]]
- [[psql]]
