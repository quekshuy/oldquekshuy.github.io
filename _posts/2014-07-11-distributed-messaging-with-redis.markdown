---
published: false
title: Distributed messaging with Redis
layout: post
---
I've been spending some time writing a small ruby library for message streaming using Redis.

__Background__

We want to stream events out to a number of services. These services will possibly process these events, do aggregation, write to data stores, etc.

There are a number of well-known systems out there by which we can do this -- Apache Storm/Kafka, Amazon Kinesis, and (i'm pushing it here) Amazon SQS + SNS. What these systems allow is that messages are duplicated to their respective consumer applications to be used accordingly.

The problem is we believe our service has not reached the scale to adopt the additional tech (complexity) that the above require. 

So we wish to write something small first, deploy that then move ahead with other stuff.

So I wrote __clarinet__ (private repo, so no link as of now).

__Description__


