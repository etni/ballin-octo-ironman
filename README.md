# MDB Course Notes

## Week 1 - Introduction

Installing mongodb 

* There should be a /data/db folder or (c:\data\db in windows)
* add mongo folder to the path
* mongod -- server. should get in habit to read the output of this program to ensure that we're connected to the right database/server. etc.
* mongo -- client. it's a javascript console

## Week 2

* mongodb internal storage is BSON. not plain text. 

* BSON spec [http://bsonspec.org/]

* update has four operations
  * wholesale update (replaces the entire record with the record). this will replace the entire record with the record passed on the second parameter.

    ```javascript
    db.users.update( {name:'test'}, { field: 'value'} )
    ```

  * set field.. only updates the fields or adds it if it doesn't exist

    ```javascript
    db.users.update( {name:'test'}, { $set: { field: 'value', field2: 'value2'}})
    ```
  * upsert: update document or insert one if it doesn't exist.

    ```javascript
    db.users.update( { name:'test'}, { field: 'value'}, {upsert: true})
    ```

  * an empty object { } works as a selector for all documents on the collection.

    the default behavior on mongodb if a selector for all documents is specified is to update only one record... unless the { multi: true} is passed as the third parameter.. for instance.

    ```javascript
    db.users.update( {}, {$set { title: 'Dr.'}})
    // this will only update one record     
    

    db.users.update( {}, {$set { title: 'Dr.'}}, {multi: true})
    // this will update all records on the collection
    ```


