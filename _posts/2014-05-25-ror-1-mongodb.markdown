---
published: true
title: RoR #1 MongoDB 
layout: post
---
I've taken on a new project that uses Ruby on Rails and Mongodb.

Just wanted to quickly pen down some interesting things.

We use [cube](http://github.com/square/cube) to do event tracking. The events are stored in Mongo.

Basically the schema of the documents in Mongo go something like this:

```!json

{
   "_id": <some_object_id>,
   "t": <timestamp_iso_compat>,
   "d": {
       "resource": "A",
       "action": "create",
       "id": <A.id>
   } 
}

```


What we want to do is return a set of 5 __distinct__ A documents in descending order of their timestamps ("t"). 

There were a few ways.

* [using `distinct`](http://api.mongodb.org/ruby/current/Mongo/Collection.html#distinct-instance_method)

  But it doesn't allow for ordering by timestamp.

* [using aggregation with the `$group` operator](https://github.com/mongodb/mongo-ruby-driver/wiki/Aggregation-Framework-Examples)

  Was hinted at by [this](http://stackoverflow.com/questions/18326345/mongodb-java-driver-distinct-with-sort) post. But found out that i thought wrong.
  `$group` doesn't allow for ordering by fields.
  ![no $group order](https://www.evernote.com/shard/s2/sh/0aff3ae4-56de-400e-b2d0-aeed23fda4f3/3f756532aa36b12960eeb335aa01dc6d/deep/0/$group-(aggregation)---MongoDB-Manual-2.6.1.png)

So in the end, the best way so far to do this is still to iterate and memoize until you have 5 unique results (either using a hash to test for uniqueness or a [Set](http://www.ruby-doc.org/stdlib-1.9.3/libdoc/set/rdoc/Set.html))

