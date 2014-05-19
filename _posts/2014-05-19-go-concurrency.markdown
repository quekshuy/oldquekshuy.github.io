---
published: false
title: Go Concurrency?
layout: post
---
I've been trying to learn Go(lang). 

In a way, the evernote-golang-sdk is taking a backseat because it requires a lot more knowledge about Thrift than it does about Go. I'll come back to it when I feel like it :p But at least my last pass on the code was to refactor such that it made use of channels and goroutines in its API. I thought that was the best arrangement because it relieved the module of dependency on receiving text on the standard input.

'Nuff said about that. I've been working on a project called [sg-go-cinema-scraper](http://www.github.com/quekshuy/sg-go-cinema-scraper).  

Basically, I make use of a super library, [goquery](http://www.github.com/PuerkitoBio/goquery), to scrape info from the few cinemas in Singapore.

There are apps out there that do this already. I could easily mitm the apps to figure out their APIs and use those instead. But I decided to take the hard way out (anyway I realized promiscuous mode on Wireshark doesn't work so well the last time I tried).

The nice thing about this project is a thorough opportunity to use goroutines and channels for synchronization and data sharing. I picked up some stuff that I felt like documenting over here:

1. __Concurrency, though easier, is still hard__