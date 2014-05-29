---
published: true
title: Ruby is the cutest language
layout: post
---
I've just had a few days with Ruby (on Rails) and I must say the experience has been interesting.

Its got all these language features that make it fun for programmers to write. No wonder so many people rave about writing Ruby. Couldn't find any performance benchmarks that were recent so I'll leave that out but Twitter used to run on RoR and now they run most of their backend on Scala (JVM ftw I guess).

Reasons Ruby is cute:

* Loops using blocks

Most languages have `for` and `while` loop constructs. Ruby has looping but the instructions to loop are attached as an object -- a block [of code]. 

_Python_

```

for i in xrange(5):
  print i

```

_Ruby_

```
5.times{ |i|
  puts i
}

```

Look at that? A lambda-esque (it's really not a lambda there are differences in Ruby) block of code is passed to a method attached to a number. You can tell that when Ruby says everything is an object, it makes damn sure that as a beginner you see it.

To be continued...