---
title: "Storage for Usage"
description: "Using the right storage for your offline (web or hybrid) app"
image: /assets/images/post-bg-09.jpg
tag: 
    - storage
    - javascript
    - offline
    - online
    - web
    - hybrid
    - app
    - localstorage
    - sqlite
    - pouchdb
    - lokijs
    - databases
    - browser
    - chrome
    - mobile
author: lagosnomad
category: blog
layout: post
headerImage: false
projects: false
hidden: false # don't count this post in blog pagination
externalLink: false
date: 2017-08-17
---
![Storage for Usage](../assets/images/post-bg-09.jpg)

# "Sto" well to avoid "rage" 

``` txt
That your awesome (Web or Hybrid) app would be awescome if 
your users could use it offline.
```

Up until now when my current employer is starting to preach about offline capable mobile apps, i have never bothered about
building offline capable apps. My employer's preaching got to me and i decided to look into developing proper offline
capable mobile apps that even support offline login and authentication and some basic crud operations.

# Spells that make it possible

Personally, i have a good habit i think other developers should also adapt. I took my time to search and understand the
different ways i could go about implementing a good solution, rather than "follow trend". Sometimes trending technology could be
the best solution too, but better understanding of all available options allows you make better and informed decisions.

After looking stuff around, i ended up with a number of options for implementation.

- Localstorage
- **[SQLite](https://www.sqlite.org)**
- **[PouchDB](http://pouchdb.com/)**
- **[LokiJS]()**

## Localstorage

Localstorage is the most common method and simples of storing in app data. It allows you to store
data in key-value pairs.

- It has a limit of 5mb accross all platforms (Android and iOS).
- You shouldn't use this for data you want to persist. iOS clears the data once the OS is low in memory
  and there are reports of data loss also on Android. If you are fetching data from a server, this would be a great way to
  save the data and usse in app rather than making multiple API calls for the same data.
- It can only store strings.
- It can store objects and array too but you'll have to convert them to JSON for storing and retrieving.

There are frameworks built on top of localstorage such as [ngStorage](https://github.com/gsklee/ngStorage)
and [localForage](https://github.com/mozilla/localForage).
A simple usage in code might look like:

```javascript
    // simple example
    localStorage.setItem('country', 'nigeria');
    var name = localStorage.getItem('country');
    console.log(name);

    // complex example
    var records = [
        {country: 'nigeria', no_of_states: 36 },
        { country: 'usa', no_of_states: 50 }
    ];
    localStorage.setItem('records', JSON.stringify(records));
    var output = JSON.parse(localStorage.getItem('records'));
    console.table(output);
```

## [SQLite](https://www.sqlite.org)

Basically, SQLite is an embedded SQL database. So rather than have your database separate from your application,
you have it in your application. If you are familiar with SQL you shouldn't have a problem with this. I'll be using
[the cordova-sqlite-storage](https://github.com/litehelpers/Cordova-sqlite-storage) as a basis for this discussion.

- It has support on all major platform.
- It uses SQL syntax, although there are **[a few differences](http://www.tutorialspoint.com/sqlite/sqlite_overview.htm)**
  between SQL and SQLite commands.
- There seems to be no limit to the size but after digging deep trying to find the limit,
  **[there was an issue](https://github.com/litehelpers/Cordova-sqlite-storage/issues/174#issuecomment-83019399)**
  raised on github that limited the size to about a 100mb.
- Data loss depends on you following good practices or not.
  **[There's a guide here on how to avoid data loss when using this as your storage](https://github.com/litehelpers/Cordova-sqlite-storage#avoiding-data-loss)**.
- Be careful with BLOBs. Find a more comprehensive
  **[note on some pitfalls here](https://github.com/litehelpers/Cordova-sqlite-storage#pitfalls)**.

A simple usage in code might look like:

```javascript
    // to open a database
    var db = null;
    document.addEventListener('deviceready', function() {
        db = window.sqlitePlugin.openDatabase({name: 'countries.db', location: 'default'});
    });

    // to populate a database
    db.transaction(function(tx) {
        tx.executeSql('CREATE TABLE IF NOT EXISTS Countries (name, no_of_states)');
        tx.executeSql('INSERT INTO Countries VALUES (?,?)', ['nigeria', 36]);
        tx.executeSql('INSERT INTO Countries VALUES (?,?)', ['usa', 50]);
    }, function(error) {
        console.log('Transaction ERROR: ' + error.message);
    }, function() {
        console.log('Populated database OK');
    });

    // to retrieve data from a database
    db.transaction(function(tx) {
        tx.executeSql('SELECT count(*) AS FROM Countries', [], function(tx, rs) {
            console.log('Record count (expected to be 2): ' + rs.rows.item(0).mycount);
        }, function(tx, error) {
        console.log('SELECT error: ' + error.message);
        });
    });
```

## **[PouchDB](http://pouchdb.com/)**

PouchDB is an open-source JavaScript database inspired by Apache CouchDB. It uses IndexedDB under the hood and falling back to WebSQL where IndexedDB isn't supported. You can use it with Angular, React, Ember, Backbone, or your framework of choice.

- It uses the NoSQL syntax.
- Supported on most modern platforms.
- Since it's NoSQL, you can directly store JSON data and retrieve it as it is.
- It can store up to 250mb of data.
- It comes with a built in function that allows you to sync your offline data with your cloud databases instances that implement a CouchDB-like protocol, and PouchDB.
- Sadly you can't sync with MongoDB yet (of date).
- BLOBs? No problem.

There are frameworks/adapters built on top of it such as
**[angular-pouchdb](https://github.com/angular-pouchdb/angular-pouchdb)**, 
**[ngPouch](https://github.com/jrhicks/ngPouch)**, **[ng-pouchdb](https://github.com/danielzen/ng-pouchdb)**, **[vue-pouch](https://github.com/qurateinc/vue-pouch)**, **[kendo-pouchdb](https://github.com/terikon/kendo-pouchdb)**, etc.
A simple usage in code might look like:

```javascript
// create a new local database
var db = new PouchDB('countries');

// create a new remote database
var db = new PouchDB('http://localhost:5984/countries');

// storing a document
var doc = {
  "_id": "c1",
  "name": "nigeria",
  "no_of_states": 36
};
db.put(doc);

// retrieving asynchronously by _id the callback way
db.get('c1', function (error, doc) {
  if (error) {
    // error stuffs
  } else {
    // do some stuff with our doc
  }
});

// retrieving asynchronously by _id using promise
db.get('c1').then(function (doc) {
  // do some stuff with our doc
}).catch(function (err) {
  // error stuffs
});
```

## LokiJS

LokiJS is a lightweight javascript document oriented database. It is intended to be used as an in-memory database, with the possibility of persisting the data.LokiJS draws inspiration from MongoDB and CouchDB, in that the API is similar (but not identical or compliant) to MongoDB. The glossary used is also classic NoSQL in that records are documents, documents are stored in collections.LokiJS supports a limited form of indexing for faster document access. The id field in particular is automaticallly populated and indexed, and searched using the binary search algorithm. Other document properties can be indexed for faster search on a particular object field.

- Fast Performance.
- Replaces SQLite in Cordova, works as a session store and full blown NoSQL.
- DB in node.js, works as in-browser database with syncing capabilities.
- Indexing, Secondary Indexing, Unique Indexing.
- The "Dynamic View", a kind of "live filter" (self-materializing views).
- Persistence Adapters (with a built-in IndexedDB and node.js FS adapter).
- Optional periodic autosave.
- Changes API which keeps track of all the changes made to the
  local database. You can use this API to synchronize our cloud database.
- Compound sort for sorting on multiple columns.

```javascript
// Creating a database
var db = new loki('example.db');

// Add a collection :
var countries = db.addCollection('countries');

// Insert documents
countries.insert({
    name: 'usa',
    no_of_states: 50,
});

// alternatively, insert array of documents
countries.insert([
    {name: 'usa', no_of_states: 50},
    {name: 'nigeria', no_of_states: 36}
]);

// Simple find query
var results = countries.find({ no_of_states: {'$gte': 36} });
var result = countries.findOne({ name: 'nigeria' });
```

# In conclusion

After my little research into these technologies and comparing the scope of the offline application i want to build, i have made a decision on the tech to use.
As developers we should do research into the tools and tech we use for projects so we don't end up with something overkill or underkill.

Cheers!!!
