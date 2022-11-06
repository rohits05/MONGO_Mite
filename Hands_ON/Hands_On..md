
# Notes Link: https://www.codewithharry.com/blogpost/mongodb-cheatsheet/

# Download Links
## Msi: https://www.mongodb.com/try/download/community 
## Mongoshell: https://www.mongodb.com/try/download/shell
## MongoDB ATLAS: https://www.mongodb.com/cloud/atlas
________________________________________________________________________________


# MongoDB Commands for Database
##  View all databases
> show dbs

## Create new database
> use rohits05 (database name)

## To verify/check the new database
> db (gives the current database)

## To delete database
> db.dropDatabase()
____________________________________________________________________________________


# MongoDB Commands for Collection
## To create collection
> db.createCollection("rohits05") (collection name)

## To View all collections
> show collections

## To create another/new collection
> db.createCollection('comics')
--------------

## To insert rows/data in collection
> db.comics.insertOne({name: "Harry Potter", author: "J.K. Rowling"})

## To insert multiple data in collection
> db.comics.insertMany([{name: "Harry Potter", author: "J.K. Rowling"}, {name: "Harry Potter", author: "J.K. Rowling"}])
--------------

## To delete collection
> db.comics.drop()

## To delete/remove data in collection
> db.comics.deleteOne({name: "Harry Potter"})

## To delete multiple data in collection
> db.comics.deleteMany({name: "Harry Potter"})

## To delete all data in collection
> db.comics.deleteMany({})
> db.comics.remove({name: "Harry Potter"})
(remove() is deprecated) 
--------------

## To Search all data in collection
> db.comics.find()

## To Search all data in collection in a better way
> db.comics.find().pretty()

## To Search all data in collection in a better way with limit
> db.comics.find().pretty().limit(2)

## To Search all data in collection in a better way with limit and skip
> db.comics.find().pretty().limit(2).skip(1)

## To Search all data in collection in a better way with limit and skip and sort
> db.comics.find().pretty().limit(2).skip(1).sort({name: 1})

## To Search all data in collection in a better way with limit and skip and sort and count
> db.comics.find().pretty().limit(2).skip(1).sort({name: 1}).count()
( 1: ascend_sort, -1: descend_sort )
## To Search all data in collection in a better way with limit and skip and sort and count and find specific data
> db.comics.find({name: "Harry Potter"}).pretty().limit(2).skip(1).sort({name: 1}).count()
--------------

## To Search only one row in the collection
> db.comics.findOne({name: "Harry Potter"})

## To Search only one row in the collection in a better way
> db.comics.findOne({name: "Harry Potter"}).pretty()

## To Search only one row in the collection in a better way with limit
> db.comics.findOne({name: "Harry Potter"}).pretty().limit(1)

## To Search only one row in the collection in a better way with limit and skip
> db.comics.findOne({name: "Harry Potter"}).pretty().limit(1).skip(1)

## To Search only one row in the collection in a better way with limit and skip and sort
> db.comics.findOne({name: "Harry Potter"}).pretty().limit(1).skip(1).sort({name: 1})
______________________________________________________________________________________________________________________


# MongoDB Commands for Update
## To update data in collection
> db.comics.updateOne({name: "Harry Potter"}, {$set: {name: "Harry Potter and the Philosopher's Stone"}})
(updateOne or update)

## To update multiple data in collection
> db.comics.updateMany({name: "Harry Potter"}, {$set: {name: "Harry Potter and the Philosopher's Stone"}})

## To update data in collection with upsert
> db.comics.updateOne({name: "Harry Potter"}, {$set: {name: "Harry Potter and the Philosopher's Stone"}}, {upsert: true})
(upsert: true means if the data is not present then it will create a new data)

## To update multiple data in collection with upsert
> db.comics.updateMany({name: "Harry Potter"}, {$set: {name: "Harry Potter and the Philosopher's Stone"}}, {upsert: true})

## To update data in collection with upsert and returnOriginal
> db.comics.updateOne({name: "Harry Potter"}, {$set: {name: "Harry Potter and the Philosopher's Stone"}}, {upsert: true, returnOriginal: false})

## To update multiple data in collection with upsert and returnOriginal
> db.comics.updateMany({name: "Harry Potter"}, {$set: {name: "Harry Potter and the Philosopher's Stone"}}, {upsert: true, returnOriginal: false})
______________________________________________________________________________________________________________________________




# MongoDB Rename Operator
## To rename data in collection
> db.comics.updateOne({name: "Harry Potter"}, {$rename: {"name": "book_name"}})

## To rename multiple data in collection
> db.comics.updateMany({name: "Harry Potter"}, {$rename: {"name": "book_name"}})
______________________________________________________________________________________________________________________________


# MongoDB Increment Operator
## To increment data in collection
> db.comics.updateOne({name: "Harry Potter"}, {$inc: {"price": 100}})

## To increment multiple data in collection
> db.comics.updateMany({name: "Harry Potter"}, {$inc: {"price": 100}})
______________________________________________________________________________________________________________________________

# MongoDB Remove Operator
## To remove data in collection
> db.comics.updateOne({name: "Harry Potter"}, {$unset: {"price": ""}})

## To remove multiple data in collection
> db.comics.updateMany({name: "Harry Potter"}, {$unset: {"price": ""}})
--------------
# MongoDB Less Than Operator  
## To search data less than in collection
> db.comics.find({price: {$lt: 100}}).pretty()

## To search data less than or equal to in collection
> db.comics.find({price: {$lte: 100}}).pretty()

## To search data greater than in collection
> db.comics.find({price: {$gt: 100}}).pretty()

## To search data greater than or equal to in collection
> db.comics.find({price: {$gte: 100}}).pretty()

## To search data not equal to in collection
> db.comics.find({price: {$ne: 100}}).pretty()

## To search data in between in collection
> db.comics.find({price: {$gt: 100, $lt: 200}}).pretty()

## To search data in between or equal to in collection
> db.comics.find({price: {$gte: 100, $lte: 200}}).pretty()
------------------------------------------------------------------------------------------------------------------------------