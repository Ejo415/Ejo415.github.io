---
layout: post
title:      "Rails amirite?"
date:       2020-10-17 12:54:55 -0400
permalink:  rails_amirite
---


Hoo boy, im not sure what it is about rails that threw me so much. Ive decided to go with "an abundance of Sinatra review with juuuuuuust enough additions to completely throw me off." I got there in the end but MAN the first few days this week I felt like I was scrambling around like a crazy person. And due to popular demand the Klass...class made a return from my Sinatra project which was just heaps of fun when it came to my join table  and nested routes (more on that later.)

After taking a breath I took a beat and had to mind myself that Rails is ultimately, Sinatra thats been fancified, with that in mind i was able to get the basic CRUD up and running in short order. Getting OAuth set up was a bit of an adventure as well as i had a few pesky before_action methods set up that was jamming me up on account creation using it. All of those hiccups aside my app (which is a Gym Class Schedule manager since i just realized i forgot to mention) has a boolean function that when checked sends a schedule reminder via email. Which to my delight was easier to set up than i was expecting. a little bit of 

`rails g mailer UserMailer`

And i was off to the races. that generated a UserMailer controller, a views folder, and layouts for HTML and plantext. after that you just have to configure a few settings and cook up your emails. First in app/mailers/user_mailer i had to set up the method call that would send my reminder


 ```
def reminder(user)
        @user = user
        mail(to: user.email, subject: 'Scheduled Class Reminder')
      end
```

then in config/enviroments/development I added these two blocks

```
config.action_mailer.perform_deliveries = true
config.action_mailer.raise_delivery_errors = true
config.action_mailer.default_options = {from: 'no-reply@example.com'}

config.action_mailer.delivery_method = :smtp
config.action_mailer.smtp_settings = {
address:              'smtp.gmail.com',
port:                 587,
domain:               'libertyhaganahcenter.com',
user_name:            '<username>',
password:             '<password>',
authentication:       'plain',
enable_starttls_auto: true  }
```

in the `user_name` and `password` fields is where you include the login information to whatever email account that is going to be sending the emails (this setup is also for gmail)

optionally after that you can set up a prevew for the configured emails in test/mailers/previews.

```
 def reminder
        UserMailer.with(user: User.find_by_id(3)).reminder(User.find_by_id(3))
      end
```

That is best I can tell a pretty general overview of setting up the Rails ActionMailer, it was far less complicated than i was expecting if im being honest.



All in all after taking a breath and (finally) getting into the groove, Rails wasnt so bad. Now that this is done I should probably go learn me some `form_with` though...

