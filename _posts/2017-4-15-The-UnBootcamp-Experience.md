---
layout: post
title: The UnBootcamp Experience!
---

Took a trip to Cross Campus DTLA to meet the UnBootcamp crew and learn a few things
Updates on the [Learn Teach Code](http://learnteachcode.org/) UnBootcamp experiment.

## Today I learned (#TIL):

- reviewed functions and nesting functions
- went over scope of variables global and local e.g. within functions
- saw a demo of node.js and setting up socket.io to run realtime js code on the backend
- how to run a real time app with socket.io and node.js (see example below)

{% highlight javascript %}

var http = require("http");
var server = http.createServer(function(request, response) {
  response.writeHead(200, {"Content-Type": "text/html"});
  response.write("<h1>Hello!</h1><p>You asked for <code>" +
                 request.url + "</code></p>");
  response.end();
});
server.listen(process.env.PORT || 8000);

//demo server: https://nodejs-test-learningnerd.c9users.io/

var http = require("http");
var request = http.request({
  hostname: "nodejs-test-learningnerd.c9users.io",
  path: "/test123.html",
  method: "GET",
  headers: {Accept: "text/html"}
}, function(response) {
  console.log("Server responded with status code",
              response.statusCode);
});
request.end();

// is socket.io library in the html file to do this on the browser?
// <script type="text/javascript" src="socket.io.js"></script>

{% endhighlight %}

- algorithms are simply ==> {a list of instructions}
- how to use algorithms, formulas and also "Math" methods e.g. Math.sqrt()
- pair programmed a function using  Pythagorean's theorem (see code below)
- using https://repl.it to toss code back and forth when pair programming

{% highlight javascript %}
  function Pythag(a, b)
      {
          console.log("Ok, side A is " + a);
          console.log("Cool, side B is " + b);
          var cSquared = (a * a + b * b);
          var c = Math.sqrt(cSquared);
          console.log("Side C is = " + c );
       }
Pythag(3,4);
{% endhighlight %}


## Questions:

- how do i put buttons in Jekyll like this picture below?
![insert witty and cool SEO pic text here...](/images/Capture.PNG)
- do i need socket.io library in the html file to run a socket.io chat site?


## Bugs discovered / what I got stuck on:

- i was stuck trying to figure out how to insert images into the posts, but this is how i did it...put the image in the images folder and commit push
{% highlight javascript %}
![insert witty and cool pic from Gordon Zhu's Watch and Code website here...](/images/Capture.PNG)
{% endhighlight %}
- stuck on this Codecademy javascript lesson on data structures all day but finally figured it out:
{% highlight javascript %}
// need help to hack and tweak code below
// change list and search function to search("Steve") and return Steve's info

var friends = {

bill:   {
firstName: "Bill",
lastName: "Gates",
number: "(206) 555-5555",
address: ['One Microsoft Way','Redmond','WA','98052']
        },

steve: {
firstName: "Steve",
lastName: "Jobs",
number: "(206) 666-5555",
address: ['One Infinite Loop','Cupertino','CA','90025']
        }
              };

//need to review part need some
var list = function(friends)
    {
        for (var key in friends)
        {console.log(key);}
    };

var search = function(name)
    {
        for (var key in friends)
        {if (friends[key].firstName === name)
            {console.log(friends[key]);
            return friends[key];
            }
        }

    };

//list(friends); //used this to see whats going on
search("Steve"); //this is supposed to return Steve's info...
{% endhighlight %}
- I needed to understand how the key thing worked with the list function
- typos, case sensitive, semicolons oh my...
- debug.time = search(needle, hayStack); //losin my mind here!

## Useful links to save for later:
- http://stackoverflow.com/questions/28820917/jekyll-on-github-pages-not-displaying-images-and-has-broken-links
- http://chariotsolutions.com/blog/post/getting-chatty-angular-socket-io-nodeexpress-bootstrap/
- https://www.html5rocks.com/en/tutorials/frameworks/angular-websockets/

## My next goals:

- get a better understanding and feel for looking up objects with keys
- work on the socket.io chat app with node.js
- learn how to read and insert to a database using node.js
- deploy chat app project to GitHub and Heroku
- more googling and videos
