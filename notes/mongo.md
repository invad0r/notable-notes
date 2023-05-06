---
tags: [database, javascript]
title: mongo
created: '2019-07-30T06:19:49.178Z'
modified: '2023-04-30T11:30:01.101Z'
---

# mongo

> `mongo` shell is an interactive javascript interface to `mongodb` used to query and update data and perform administrative operations

## install

```sh
```

## option

```sh
```

## usage

```sh
mongo "mongodb://HOST:28015"

mongo 'mongodb://USER:PASS@HOST1:PORT,PASS@HOST2:PORT,PASS@HOST3:POR/DATABASE?replicaSet=RELICASET&ssl=true&authSource=admin'

mongo --host=HOST --port=27017

mongo --username admin --password --authenticationDatabase admin --host HOST --port 27017

mongo --help 	            # show command line options

mongo --nodb 	            # start mongo shell without connecting to a database

mongo --shell             # used in conjunction with a javascript file (FILE.js) to continue in the mongo shell after running the FILE.js
````

## mongo shell

```js
help                 // show help

show dbs             // show database names

show collections     // show collections in current database

show users           // show users in current database

show profile         // show most recent system.profile entries with time >= 1ms

show logs            // show the accessible logger names

show log [name]      // prints out the last segment of log in memory, 'global' is default


use DATABASE                              // select DATABASE


db.runCommand("ismaster")                       // find out master node
rs.isMaster().primary                           // find out master node
rs.stepDown(60)                                 // cause a new master to be elected, not be eligible for re-election for 60s
rs.status().members.find(r=>r.state===1).name   // current primary server's IP


db                                        // list current database

db.adminCommand( { listDatabases: 1 } )   // list databases

db.help()                                 // help on db methods

db.serverStatus().storageEngine           // get current storage engine

db.currentOp().inprog[0].msg              // progress while indexing

db.repairDatabase()                       // free up space on `mmapv1` 
db.runCommand({repairDatabase: 1})

db.stats
db.stats(1024).storageSize


db.test.count();


db.getCollection('COLLECTION').find({})

// edit multiple fields
db.getCollection('executions').update({"state":"ERROR"}, {"$set": {"state":"NO_ERROR"} }, {multi: true})                                 

db.getCollection('executions').find({'state': 'ERROR'}, {state: 1, _id: 0}).toArray()

db.getCollection('COLLECTION').count({state: "EXECUTING"})          // count

db.getCollection('COLLECTION').find({}).sort({_id: -1}).limit(1);   // get last item of collection


db.getCollection('COLLECTION').find({email: /^foo/})          // find where email starts with foo
db.getCollection('COLLECTION').find({email: /^ma.*l$/})   
// .* means to match 0 or more of any character
//  matches string that starts with "ma" and ends with "l", ignoring whatever is between.
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

- [[mongosh]]
- [[mongod]]
- [[mongodump]]
- [[mysql]]
- [[psql]]
- [docs.mongodb.com/manual/reference/mongo-shell/#command-helpers](https://docs.mongodb.com/manual/reference/mongo-shell/#command-helpers)
- [scalegrid.io/blog/understanding-managing-disk-space-on-your-mongodb-server](https://scalegrid.io/blog/understanding-managing-disk-space-on-your-mongodb-server/)

