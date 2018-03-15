---
title: "GraphQL and Chill"
description: "Quick thoughts on GraphQL"
image: /assets/images/post-bg-11.jpg
tag: 
    - graphql
    - PWA
    - REST
    - API
author: lagosnomad
category: blog
layout: post
headerImage: false
projects: false
hidden: false # don't count this post in blog pagination
externalLink: false
date: 2017-08-31
---
![GraphQL and Chill](../assets/images/post-bg-11.jpg)

Yaay guys, this will be the first guest post on my blog and I'm super excited.
I got a request from a friend. He had been following up with my post and wanted to feature, so why not?

# Let's Meet [Ajani Eniola](https://twitter.com/ajani_eniola)

I'm Ajani Eniola and here are a couple of interesting things about me:

- Progressive Web Application (PWA) Developer.
- I also do MEAN Stack Development.
- I preach RxJS observables.
- I'm probably one of the few tall guys in the world that don't play basketball.
- I love slow music too.

## Inspiration

**Can [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) truly be replaced?**

If you had asked me this question exactly 9:05 am August 11 2017, trust me my reply would have been *“ko le work”*.

I should have been at the last meetup at Andela but because of a couple of unplanned events, I was unable to attend.
While going through pictures from the event on twitter, I saw a slide from a presentation made by [**@timigod**](https://twitter.com/timigod) on [**GraphQL**](http://graphql.org/). Since then, I picked up interest in it and also discovered technologies like [**Apollo**](https://www.npmjs.com/package/appolo) and [**Relay**](https://facebook.github.io/relay/).

## [GraphQL](http://graphql.org) Experience

GraphQL has been around since 2012 and used internally at [**Facebook**](https://www.facebook.com) but became open source for the public this year. Big boys like [**Github**](https://github.com) currently have their public APIs built on GraphQL.

While getting my hands dirty, I played around with [**GraphCool**](https://www.graph.cool/) and [**Scaphold**](https://scaphold.io/) which are pretty good GraphQL Servers.

After some reading and trial and errors, I was able to build my own graphql server using [**MongoDB**](https://www.mongodb.com/), [**Express JS**](https://expressjs.com) and [**NodeJS**](https://nodejs.org). I hooked this spectacular backend to my front end that runs on [**angular2 apollo**](https://www.npmjs.com/package/angular2-apollo) for handling request from the GraphQL backend.

The purpose of this experiment was to compare the time required for both a GraphQL Server and A RESTful API to handle and process a request. After setting up the two different environment, the GraphQL server used 5.22ms to return data to the client, while the RESTful API took 131.87ms to return the same data to the same client. I bet even **The Flash** can't beat that!!!

# In conclusion

In terms of access to the open source community, GraphQL is still in its early stages. There are still a lot of debates about it which will have effects on the adoption rate, but from this basic experiment, it is safe to say GraphQL is very fast in fetching data from a server and should be given a shot by developers.

# Development

[My GraphQL server](https://github.com/ajanieniolasolomon/graphql-) is hosted on Github.

Want to contribute? Great!
Fork [the project](https://github.com/ajanieniolasolomon/graphql-) and send in a pull request.

Also feel free to [Tweet at me](https://twitter.com/ajani_eniola), I'll be glad to brainstorm with you.

Cheers!!!
