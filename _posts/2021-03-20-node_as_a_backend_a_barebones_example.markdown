---
layout: post
title:      "Node as a backend: a barebones example."
date:       2021-03-20 21:53:40 +0000
permalink:  node_as_a_backend_a_barebones_example
---


Alright, I said I would be bringing you along as I suss my way through Node, so here's a simple stumped out basic backend using Node.js (read: a suuuuuuper barebones ugly non refined will be expanded upon later with a framework backend) 

First we want to import the http module which allows us to create a server and make http requests, so we'll store that in a const.

`const http = require('http');`

next we're going to make our server, also stored in a const, most of the server configuration will be kept here.

```
const server = http.createServer((req, res) => {

}
```

`createServer` takes two arguments, a request and a response. So now that we have our server object defined we can set it up with a port to work out of, this will exist outside of the createServer method.

`server.listen(3000) `

That is what allows you to spin up your server and it will work out of (in this case, you can set whatever port youd like) port 3000, so going to localhose:3000 will get you your backend if you need to evaluate the API as you work later on.

Now lets get back to setting up our server, since we're still in development lets throw in a couple console.logs to fire off when a request is made and what kind of request is made, so
 
`console.log('Incoming Request')` followed by `console.log(req.method)`. So now we should have 

```
const server = http.createServer((req, res) => {

console.log('Incoming Request')
console.log(req.method)

}
```

Now if you run this and any request is made its going to time out because we're not sending a response. Thats where `res.end `comes in.

For the sake of this hilariously simple example we're just gonna send a text response back.

`res.end('I am a hilariously simple example of a server response')`

so when you fire up your server this is what the page will read. But just to introduce headers now we can also add

`res.setHeader('Content-Type', 'text/html');`

just above that so we can control whats sent back. (odds are you'll use json when you're actually building anything out.)

altogether we should have 

```
const http = require('http');

const server = http.createServer((req, res) => {

console.log('Incoming Request')
console.log(req.method)

res.setHeader('Content-Type', 'text/html');
res.end('I am a hilariously simple and borderline condecending example of a server response')
}

server.listen(3000)
```

There will be more in the future, I may even get saucy and include recieving data and parsing it BEFORE I move on to the Express framework. You'll just have to wait and see. Till next time.

(PS Jury duty was stupid)
