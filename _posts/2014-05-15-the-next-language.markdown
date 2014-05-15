---
published: true
title: The next language
layout: post
---
I've been job hunting. While the world of software development is ripe with opportunity, I'm going to lay it out for you: your choice of expertise in a programming language matters. This despite a lot of wisdom floating around online that __you should use the right tool for the right problem__. Yeah, but what if your familiarity with the tool shows that you've been solving problems that the company you're applying to is not interested in. 

So here's more about why I say this (note: I'm saying this from the perspective of someone applying for a general software development position):

* __Only big tech doesn't care about what language you used to write. For the rest of the world, it matters.__

   Lots of startups and small to medium enterprises want hires to be effective immediately. This means they want you to cut down on the time needed to ramp up in terms of the language you are using, etc. So what you've been working with for the past few months/years suddenly has more relevance.

   OK so I tried applying to roles for which I have _domain knowledge_ but no specific knowledge of the stack they use. Are the two actually the same? Maybe, but I think when it comes to the stacks for web services, the differences are not as great as they seem. Especially if they use stacks that are so damn popular, it seems the whole world has blogged/documented how things can get done.

* __Language maturity has correlation to toolset maturity__

  I've been trying to learn [Go](http://golang.org/) recently. I've been trying to figure out Thrift so I can write something resembling an [SDK for evernote in Go](http://github.com/quekshuy/evernote-golang-sdk). That's my 30mins of coding everyday project. Not going well I might like to add.

   But because Go was only released a few years ago, and although it has all the right things going for it, the toolsets built using it are also similarly not as mature. [Recently Braintree tried porting a service to Go and found challenges doing things quickly](https://www.braintreepayments.com/braintrust/gotchas-irritants-and-warts-in-go-web-development). So while just pure systems that do concurrent processing of data will make sense in this language, a lot of other things that require interfacing with other technologies may not.

  I'm going to start learning Scala just to see if there's some advantage in terms of speed of development, because I'm hoping more packages have been developed.

* __Language represents domain__

Back to how I started this: you solve problems with a particular language/toolset, you've automatically been associated with the problem domain. While this is obvious, it might be an additional consideration. Java (JVM) and .NET is for the enterprise; Python and Ruby are for web startups (general computing); CMSes and e-commerce outfits still turn to PHP as their language of choice; C/C++ for embedded systems and firmware. Not surprising but if you've picked your poison and worked with one exclusively for the bulk of your career without experimenting with others, you might find switching fields a tad difficult. Unless you have built an extensive portfolio outside of your work of course.



