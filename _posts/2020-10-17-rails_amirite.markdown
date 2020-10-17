---
layout: post
title:      "Rails amirite?"
date:       2020-10-17 16:54:55 +0000
permalink:  rails_amirite
---


Hoo boy, im not sure what it is about rails that threw me so much. Ive decided to go with "an abundance of Sinatra review with juuuuuuust enough additions to completely throw me off." I got there in the end but MAN the first few days this week I felt like I was scrambling around like a crazy person. And due to popular demand the Klass...class made a return from my Sinatra project which was just heaps of fun when it came to my join table  and nested routes (more on that later.)

After taking a breath I took a beat and had to mind myself that Rails is ultimately, Sinatra thats been fancified, with that in mind i was able to get the basic CRUD up and running in short order. Getting OAuth set up was a bit of an adventure as well as i had a few pesky before_action methods set up that was jamming me up on account creation using it. All of those hiccups aside my app (which is a Gym Class Schedule manager since i just realized i forgot to mention) has a boolean function that when checked sends a schedule reminder via email. Which to my delight was easier to set up than i was expecting. a little bit of 

`rails g mailer UserMailer`

And i was off to the races. that generated a UserMailer controller, a views folder, and layouts for HTML and plantext. after that you just have to configure a few settings and cook up your emails (ill add those in shortly)




All in all after taking a breath and (finally) getting into the groove, Rails wasnt so bad. Now that this is done I should probably go learn me so form_with though...

