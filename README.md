MongoDB

NoSQL Database - Document Database Type in NoSQL
Data is stored in json like syntax

Good to use when there is no ton of inter connected relations

Database, Collections, Document

data/db folder inside MongoDB

Run mongod and mongo in another terminal
$ mongod -directoryperdb --dbpath C:\mongodb\data\db --logpath C:\monodb\log\mongo.log --logappend --rest --install
$ net start MongoDB

$ mongo

> show dbs
> use <db_name>
> db.createUser({ user: "", pwd: "", roles: [ "readwrite", "dbAdmin" ] });

> show collections
> db.createCollection('<collection_name>');

> db.<collection_name>.insert({ });
> db.<collection_name>.insert([ { }, { }, { } ]);

> db.<collection_name>.find();
> db.<collection_name>.find().pretty();
> db.<collection_name>.find().count();
> db.<collection_name>.find().limit(4);

> db.<collection_name>.findById(id);
> db.<collection_name>.find(<matchObject>);
> db.<collection_name>.find({ "nestedObj.field": "" });

> db.<collection_name>.find({ $or: [ <matchObject1>, <matchObject2> ] });
> db.<collection_name>.find({ age: { $gt: 40 }}); // gt or gte
> db.<collection_name>.find({ age: { $lt: 40 }}); // lt or lte
> db.<collection_name>.find().sort({ field: 1 }); // ascending order is indicated by 1

> db.<collection_name>.update(<matchObject>, {}); // matchObject: { first_name: '' } 
> db.<collection_name>.update(<matchObject>, {}, { upsert: true }); // insert if not found

> db.<collection_name>.update(<matchObject>, { $set: { } }); // Preserves rest of the data in the Document
> db.<collection_name>.update(<matchObject>, { $inc: { age: 5 } } ); // increments age by 5
> db.<collection_name>.update(<matchObject>, { $unset: { age: 1 } } ); // deletes age field
> db.<collection_name>.update(<matchObject>, { $rename: { "field1": "field2" }});

> db.<collection_name>.remove(<matchObject>);
> db.<collection_name>.remove(<matchObject>, { justOne: true });

> db.<collection_name>.find().forEach(function(doc) {
    print("Customer Name": + doc.field);
  });
