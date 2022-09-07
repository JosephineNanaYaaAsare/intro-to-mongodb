# MongoDB Cheatsheet

Show the version of database server

```
  db.version()
```

Returns some statistics about
mongoDB server

```
   db.stat()
```

LIst all the database in the MongoDB server

```
  show dbs
```

Switch to uses the ddatabase specified

```
  use <dbName>
```

Create new collections in database

```
  db.createCollections("name")
```

List all collections under the specified database

```
  show collections
```

### Inserting document

Insert one document into the colection

```
   insertOne({...})
   Syntax:
     db.<collectionName>.insertOne({})
```

Insert many documents into the collection.

```
  insertMany([{}, {} ... {}])
  Syntax:
  db.<colletionName>.insertMany([ {}, {} ... {}])
```

## Finding document in collection

Returns all the documents in the collection that matches the query. It will return an empty array if there is no document in the collection. If empty object ({}) is passed as query it will return all the documents in the collection.

```
find({query})
```

Returns a single document that matches the query

```
   findOne  ({ query })
```

## Query methods

Are methods helper methods of the find method. It needs to be chained after the find() method

Sorts documents in either ascending or descending order

```
  sort()
```

Limits the returning documents to the number specified

```
  limit()
```

Skips the first number of items specified

```
   skip()
```

Counts the number of documents returned from a find result

```
  count()
```

## Equality Query

Match by field name and it’s exact value

```
  Syntax
   {<fieldName1> :  <value1>, <fieldName1> :  <value1>}

  Example
   {“name”:  “John Doe” }
   {“age”:  30}
   {“gender”: “male”,  “maritalStatus” :  “single”}
```

## Query Operator

```
 $or			$eq				$lt
 $and			$ne				$gt
 $gte			$lte			$in
 $nin			$regex
```

## Comparison Operators

Operators add conditions that compares two or more values

```
  Syntax
   {<fieldName1>: {<operator1>: <value1>}, …}

  Examples
   {“age”: {$gt : 25}}
   {“age”: {$lt : 25}}
   {“favouriteFruit”: {“$in”: [“apple”, “orange”]}}
```

## "and" Operator
Logically combines multiple conditions. Resulting documents must much ALL conditions

```
  Syntax
   { $and: [ { <condition1> }, { <condition2> } … ] }

  Example
   { $and: [ {“gender” : “male”} , “age” : 25 } ] }
```

**NB**
Explicit $and MUST be used if conditions contains same field or operator
