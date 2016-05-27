---
layout: post
title: Revivification
date: 2012-03-18 21:37
author: admin
comments: true
categories: [CouchDB, JavaScript, Programming, Programming]
---
Hello Blog.  Welcome to 2012.

So world.  How have you been?  Me?  I've been out of touch.

You see... things got pretty hectic there for a while finishing up my latest video game.  Granted it shipped over a month ago and I have had a little vacation since then, but it seems to take longer and longer as I get older to recover from the finaling push.  That isn't to say that I am enjoying it any less, it just takes a little longer to recover.

Lately I have been on sort of a digital walkabout.  Poking around the programming world to see what is new, interesting and different.  In search of the ever elusive wind that rekindles the embers of programming passion.

A word of warning: this entry is going to contain lots and lots of links to additional information for those who aren't familiar with everything I'm going to talk about.

One thing that I have been playing with is <a href="http://couchdb.apache.org/">CouchDB</a>.  CouchDB is one of the new generation of <a href="http://en.wikipedia.org/wiki/NoSQL">NoSQL</a> databases.  Which is just another way of saying a non-relational databases.  A relational database stores everything in terms of tables of relations, where a relation is defined as a list of tuples (ordered lists of elements); and a table is a list of relations where each relation always has the same number of elements.  

That sentence sort of got away from me there.

CouchDB on the other hand stores everything as documents.  Every database entry can have as much or as little data stored in any type of hierarchy that it wants.  This is incredibly flexible and powerful!  

CouchDB  stores everything internally as <a href="http://en.wikipedia.org/wiki/JSON">JSON</a> documents.  JSON is short for JavaScript Object Notation; which really just means it is a way to represent all of the elements of the JavaScript programming language in a text format.  Fundamentally it is a markup language like <a href="http://en.wikipedia.org/wiki/HTML">HTML</a> or <a href="http://en.wikipedia.org/wiki/XML">XML</a>.

This means you can have lists, dictionaries (key/value pairs), all kinds of data structures packed away in there; all mashed around in any form you want to suit your needs.  You can even reference other documents just like you would other tables in a traditional relational database.

Another great thing about CouchDB is that it is really built from the web, for the web.  By that I mean it uses <a href="http://en.wikipedia.org/wiki/HTTP">HTTP</a> and JavaScript for everything.  That's pretty much how the entire internet works.  This web page you are looking at right now?  You got it through HTTP.  It has a ton of JavaScript to make it more dynamic and pull in things like Twitter over there in the side bar.  Granted this site also has a bunch of <a href="http://www.php.net/">PHP</a>(another programming language) in it, but we'll leave that alone for now.

I had been following CouchDB from the sidelines for a while and decided to dive in and try it out.  I didn't want to bother hosting my own database to get started with so I headed over to <a href="http://www.iriscouch.com/">IrisCouch</a> to sign up for a free hosted CouchDB database (is database redundant there?  Probably). 

I decided to write a little application that could take a list of TV episodes and track what I have and haven't watched yet.  I like TV, but now that I watch it on cable, DVD, Blu-ray, Hulu, Netflix and other sites.  It gets hard to keep track of things.  Especially when one show pulls you away from everything else for a while; say a month or a year.  You can easily forget where you left off (I'm looking at you <a href="http://abc.go.com/shows/greys-anatomy">Grey's Anatomy</a>!)

So I picked my language of choice and got to work.  For those who are curious, I picked <a href="http://www.python.org/">Python</a>.  Why did I pick Python?  Because Python is full of AWESOME!  If you want to get something knocked out quickly, it is to me the best way to go.  

I put together a list of all of the shows, seasons, and episodes that I cared about as a test.  Then I wrote a quick script in Python to create 'Show' documents.  Each 'Show' holds its 'Season's, which hold their 'Episode's.  I used the excellent <a href="http://code.google.com/p/couchdb-python/">couchdb-python</a> to do the heavy lifting of connecting to the remote CouchDB, creating the database and uploading the documents.  The entire script was less than 100 lines of code, and I use a lot of blank lines.  I guess I just like negative space.

Then I put together a simple web page that used JavaScript to query the information from the database.  In CouchDB a query is just a function which you write in JavaScript that iterates over all of the elements in the database.  As it iterates over them you look at each document passed in and decide if it has what you want.  If it does, then you have the chance to create a new representation of the data on the fly (maybe you just want to pull out a couple pieces of information) or just pass through the whole document.  CouchDB actually calls it a View, because it is a view of your data, but doesn't have to be everything.  It is simple and brilliant!  JavaScript on the back end.  JavaScript on the front end.  

You can even edit your queries in real time with temporary views.

The end result?  In a few hours I had thrown together a really simple, and <em>ugly</em>, site that met all of my needs.  Want to see?  Here is my quick little <a href="http://wrath.iriscouch.com/tvdb/_design/list/index.html">tvdb</a>.  Obviously it still needs some love and attention.  Will it ever get it?  Who knows?

I had a lot of fun with my little side project!  I learned a lot and now have crazy ideas for things I could do with this type of database!

Well, if anyone is still here, I'll try not to make all of my entries quite so tech heavy.

-The End-

