---
published: true
title: MongoDB Lesson 1
layout: post
---

Here’s the stack:

RoR => [Cube](http://github.com/square/cube) => MongoDB (for storing events)

Here’s the schema of an event stored:

```
{
   “_id”: <Mongo_object_id>,
   “t”: <iso_timestamp>,
   “d”: {
      “resource”: “A”,
      “action”: “create”,
      “id”: <A_instance_id>
   }
}

```

Task:

To get 5 `distinct` instances of A with action=`create`, ordered in descending order of timestamp `t`.



Tries:

* [`distinct` in MongoDB](http://api.mongodb.org/ruby/current/Mongo/Collection.html#distinct-instance_method)

    Didn’t work because `distinct` doesn’t allow for ordering. I thought the `options` hash could allow specification of some kind or sort parameter but turns out I was wrong.

* `$group` operator in MongoDB aggregation.

    `$group` doesn’t allow for ordering as well.

  ![image?](https://www.evernote.com/shard/s2/sh/0aff3ae4-56de-400e-b2d0-aeed23fda4f3/3f756532aa36b12960eeb335aa01dc6d/deep/0/$group-(aggregation\))

[I thought this gave me a chance](http://stackoverflow.com/questions/18326345/mongodb-java-driver-distinct-with-sort), but I was evidently wrong because it was sorting the wrong things.

So ultimately I’m stuck with just doing a normal sorted query then iterating and memoizing `id`s encountered so I don’t have duplicates.