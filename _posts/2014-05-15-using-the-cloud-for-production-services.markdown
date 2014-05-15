---
published: true
title: Using the cloud for production services
layout: post
---
Tons of people use IaaS for their production services. Netflix, Dropbox ... and the list continues.

Take a look at [this](http://elekslabs.com/2014/05/how-azure-web-sites-sucked-in-production.html)

It seems like the site wasn't even operating at the scale of the aforementioned companies.

What's up?

When we were running our tiny tiny service before shuttering the company, we faced problems with AWS as well.

For one, the whole instance was stopped and we weren't informed. I'm pretty sure I wasn't the one who shut it down. In fact, I was the only one who knew which instance went down.

At a recent AWS sharing session, I questioned some local evangelists about the problem. They had not heard anyone encountering the same thing. It could also be because the people who did refused to fork out for paid support, so the issues weren't escalated. Or they could have patched the problem, thinking "oh, no harm done".

So that's the slippery slope when it comes to cloud hosting.