# MDB Course Notes

## Week 1 - Introduction

Installing mongodb 

* There should be a /data/db folder or (c:\data\db in windows)
* add mongo folder to the path
* mongod -- server. should get in habit to read the output of this program to ensure that we're connected to the right database/server. etc.
* mongo -- client. it's a javascript console

## Week 2

* mongo does not stores text but on the BSON spec http://bsonspec.org/

* upsert: update, or insert if not exists.

* update has four operations
  * wholesale update (replaces the entire record with the record)

    db.users.update( {name:'test'}, { field: 'value'} )

this will replace the entire record with the record passed on the second parameter.

  * set field.. only updates the fields or adds it if it doesn't exist

    db.users.update( {name:'test'}, { $set: { field: 'value', field2: 'value2'}})

  * upsert: update document or insert one if it doesn't exist.

    db.users.update( { name:'test'}, { field: 'value'}, {upsert: true})




