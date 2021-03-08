---
layout: post
title:      "Setting up postgreSQL and YOU!"
date:       2021-03-05 18:47:34 -0500
permalink:  setting_up_postgresql_and_you
---


Ok so at some point theres every chance in the world you'll begin using postgreSQL for your Rails backend database. In THAT event you'll need to plug your credentials into your `database.yml` file and ittl look something like this:


```

default: &default
  adapter: postgresql
  encoding: unicode
  # For details on connection pooling, see Rails configuration guide
  # https://guides.rubyonrails.org/configuring.html#database-pooling
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>

development:
  <<: *default
  database: *project name*_development
  host: localhost
  user: *username*
  password: *password*

test:
  <<: *default
  database: *project name*_test
  host: localhost
  user: *username*
  password: *password*

production:
  <<: *default
  database: *project name*_production
  username: *project name*
  password: <%= ENV['*project name*_DATABASE_PASSWORD'] %>
```
	


That was alot so let me zoom in on the important bits


```
development:
  <<: *default
  database: *project name*_development
  host: localhost
  user: *username*
  password: *password*
```

and 


```
test:
  <<: *default
  database: *project name*_test
  host: localhost
  user: *username*
  password: *password*
```



unless you do something you'll have to commit your postgreSQL credentials to your repo and thats not the greatest thing ever. Enter: the dotenv gem.

throw `gem 'dotenv-rails'` into your gemfile and run bundle install  and bobs your uncle.

but we're not done yet.

from there you want to make a `.env` file in the root of your directory and then add that` .env` to the `.gitignore`

NOW the .env and anthing in it will be ignored by git and not be uploaded into your repo on github.

Go into your .env file and add  `POSTGRES_USER=*whatever your username is*`  and  ` POSTGRES_PASS=*whatever your password is*`

 (note `POSTGRES_USER` and `POSTGRES_PASS` are just variables your setting so they can be anything I just do this so its easy to keep track of if you have multiple things in your `.env` such as oauth credentials)
 
 We're almost done I swear, sit back a sec and take a breath.
 
 Ready?
 
 Ok now go back to your `database.yml` file where it asks for the user: and password: do this:
 
 ```
development:
  <<: *default
  database: *project name*_development
  host: localhost
  user: <%= ENV['POSTGRES_USER'] %>
  password: <%= ENV['POSTGRES_PASS'] %>


test:
  <<: *default
  database: *project name*_test
  host: localhost
    user: <%= ENV['POSTGRES_USER'] %>
  password: <%= ENV['POSTGRES_PASS'] %>
```

Congratulations! You've just prevented the theft of your own data!

Till next time dear viewers.





