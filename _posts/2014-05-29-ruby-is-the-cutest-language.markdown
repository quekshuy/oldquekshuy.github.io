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


* Convenience everywhere

I remember when I was in high school how I thought languages like Java were polluting the world of programming. This was because I felt that the use of included libraries was rampant. I felt at the time that programming wasn't about encyclopedic knowledge of library functions; that was a sure sign of making you lazier as a programmer.

Then I went to university (about 4 years after that) and realise that included libraries made the act of creation much faster. Programming was a means to an end. Included libraries were code that had been tested and proven to work, so you could concentrate on the act of creation, using the various blocks that have been prepared to make even greater things. This made me appreciate Python as a language, with almost everything baked in.

Ruby is much like Python. Take for example this method built into arrays.

```
x = [1,2,3,4,5].sample
```
The above is from Ruby 1.9+.

It returns a random element of the array.

There are tons of other examples but this is the one that i recently found. It makes testing so much easier.

* Closures: blocks, lambdas, Procs


to be continued...