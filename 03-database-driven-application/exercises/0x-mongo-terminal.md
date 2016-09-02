# MongoDB in the terminal

## Introduction

[MongoDB](https://www.mongodb.com/) is a free and open-source document-oriented databse. Data in MongoDB is stored in JSON-like documents with dynamic schemas.

### Installation

```Brew update``` and ```Brew install mongo``` should pretty much do it. Then ```mkdir /data/db```. If you run into permissions problems, ```chmod 777 /data/db```. Sudo may be required. ```npm install mongo-hacker``` can also be useful.

### Documents and Collections

In mongo, each database can be broken into multiple collections. For example, a database containing information about an NSS class could have a collection for students and a collection for teachers. Each collection will contain individual documents. A student document might contain information such as name, favorite color, birthday, and a list of likes. The data in each document is stored in JSON-like format. The values in each key : value pair can be almost any type (string, number, object, array, etc). In addition to the key : value pairs that you add, mongo will automatically add a key of "_id" with a unique  identifier. Since Mongo has a dynamic schema, documents within the same collection are NOT required to have the exact same sets of keys.

### Inserting Data

In order to [.insert()] data, make sure you ```use [name of database]```, then ```db.[name of collection].insesrt()``` and pass it the information you wish to insert in a json format. For example:
```
use nssClass
db.teachers.insert({
  name: "Scott",
  likes: ["Moe's", "koala bears", "javaScript"]
})
```

### Finding (Querying) data

The [.find()] method takes two arguments, the query, which specifies which fields of the document to search, and the projection, which specifies which fields to display. For Example:
```
db.teachers.find({name: "Scott"}, {name: true})
```
The query above returns the _id field and name. The _id is always returned unless specifically set to false.
### Updating Data

The .update() method accepts a query and a json object of information. BEWARE, if you do not use the ```$set``` query operator, the entire document will be replaced by the json you pass to the update().

### More Mongo

## Topics Covered

-   Installation
-   Documents and Collections
-   .insert()
-   .find()
-   .update()
-   Mongo Extras

## Requirements

Find out stuff using a database.

## Additional Reading

-   [MongoDB](https://www.mongodb.com/)
-   [Keys](http://stackoverflow.com/questions/2298870/mongodb-get-names-of-all-keys-in-collection)
-   [.insert()](https://docs.mongodb.com/manual/reference/method/db.collection.insert/)
-   [.find()](https://docs.mongodb.com/manual/reference/method/db.collection.find/)
-   [.update()](https://docs.mongodb.com/manual/reference/method/db.collection.insert/)