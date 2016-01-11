mongod
mongo

use challenges

db.createCollection("more queries")
db.morequeries.insert(<bios data>)

check that data has been inserted:
db.morequeries.find()

remove least favorite scientist:
db.morequeries.remove({_id:9})

add new award for favorite scientist:
db.morequeries.update( {_id:10}, {$set: { awards:[ {award: "Scientist With The Least Awards", year: 2016, by: "Charlotte"}] } } )

get count of bios that have awards with years after 1991:
db.morequeries.find({"awards":{$elemMatch:{"year":{$gt:1991}}}}).count()

add this count to morequeries collection:
db.morequeries.insert({"count for docs with awards after 1991":{count: 6}})


