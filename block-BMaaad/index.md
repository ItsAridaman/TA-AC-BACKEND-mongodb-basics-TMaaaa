writeCode

Write command to

- List collections from a database.
- create a new collection in your country database which you created recently.

Write code to:-

- crate a database named `weather`
- create a capped collection named `temperature` with maximum of 3 documents and try inserting more than 3 to see the result.
- create a simple collection named `humidity`
- check whether `temperature` collection is capped or not ?
- Delete `humidity` collection and then the entire database(weather).


<!-- /////////////////////////////////// -->

> use weather
switched to db weather
> show collections
> db
weather
> db.createCollection('temperature')
{ "ok" : 1 }
> show collections
temperature
> db
weather
> db.temperature.insert({title:'node-1'})
WriteResult({ "nInserted" : 1 })
> show collections
temperature
> db.temperature.find()
{ "_id" : ObjectId("62ac57cbb536b398a3840c0d"), "title" : "node-1" }
> db.temperature.insert({title:'node-2'})
WriteResult({ "nInserted" : 1 })
> db.temperature.insert({title:'node-3'}
... ^C

> db.temperature.find();
{ "_id" : ObjectId("62ac57cbb536b398a3840c0d"), "title" : "node-1" }
{ "_id" : ObjectId("62ac5821b536b398a3840c0e"), "title" : "node-2" }
> db.temperature.insert({title:'node-3'})
WriteResult({ "nInserted" : 1 })
> db.temperature.find();
{ "_id" : ObjectId("62ac57cbb536b398a3840c0d"), "title" : "node-1" }
{ "_id" : ObjectId("62ac5821b536b398a3840c0e"), "title" : "node-2" }
{ "_id" : ObjectId("62ac5860b536b398a3840c0f"), "title" : "node-3" }
> db.createCollection('humidity')
{ "ok" : 1 }
> db.humidity.drop()
true
> show collections
temperature
> db.dropweather()
uncaught exception: TypeError: db.dropweather is not a function :
@(shell):1:1
> db.dropDatabase()
{ "ok" : 1 }
> show dbs
India   0.000GB
admin   0.000GB
config  0.000GB
local   0.000GB
