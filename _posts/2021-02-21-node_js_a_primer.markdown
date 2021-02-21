---
layout: post
title:      "Node.js: a primer"
date:       2021-02-21 17:47:52 +0000
permalink:  node_js_a_primer
---


Hello again dear readers, back with another installment of "have an overview of this thing im still learning" 

Chapter 2: Node.js

Node was far and away the top of my list of things to learn as soon as I could, from what I had been told and what I had read it seemed like a much cleaner solution for a backend if you're running anything JS as a front. And wouldnt ya know it, looks like im right.

So, imagine a single line at a store. Its backed up because the person at the regster has to process every person individually and in order, thats essentially how most other platforms (including Rails) handles requests, this is called blocking input/output(i/o). Node on the other hand uses a non-blocking i/o system to handle requests so imagine now that that store has 5 registers open at once to better handle traffic. Node handles all of its requests asynchronously so it can better handle the traffic. 

Node is also highly scalable and used by many large companies, for example when PayPal moved one of their programs over to using node they found that it was built twice as fast with fewer people, used 33% fewer lines of code, 40% less files and more importantly was able to double the amount of reqests per second with a 35% faster response time. All a benefit of using Node in a full stack enviroment with a JS front end (such as React or Angular) so code can be reused in the front and back and share file imports. On top of that you can very easily switch out which version of Node you want to use depending on what your project is almost on the fly.

Im definitely excited to dig deeper into all of this because I have a feeling once I get the hang of using Node its all im going to want to use going forward.

My apologies to Rails.
