---
title: "Mama PUT, Aboki PATCH"
description: "Understanding PUT and PATCH while building APIs"
image: /assets/images/post-bg-12.jpg
tag: 
    - REST
    - API
    - HTTP
    - aboki
author: lagosnomad
category: blog
layout: post
headerImage: false
projects: false
hidden: false # don't count this post in blog pagination
externalLink: false
date: 2017-09-20
---
![Mama PUT, Aboki PATCH](../assets/images/post-bg-12.jpg)

Lol, I very much know the title of this blog sounds out of place but don't pay much attention to it just yet.

# Big terms used in this post

Below are some of the big words in this post:

- **Mama Put:** The local food vendor that sells the most delicious food in your area. If you are in Lagos, Nigeria, **[this is a list of the best Mama Puts in town](https://blog.ofadaa.com/best-buka-mama-put-joints-lagos/)**.
- **Aboki:** An **[Hausa](https://en.wikipedia.org/wiki/Hausa_language)** word that means *"Friend"*. But in Lagos, it's used to refer to men from the Hausa tribe from the Northern part of Nigeria that do menial jobs like **[Okada](https://en.wikipedia.org/wiki/Okada_(motorcycle_taxi))** driving, sewing of clothes in a local area, waste disposal and management, etc.
- **Iya Tunde:** The name of the Mama Put in my area.
- **Idempotency:** It has nothing to do with being potent or not. Just see it as a flashy word for now.


# Inspiration for this post and title

Last Saturday, i had nowhere to go to and was super lazy. After dragging myself off my bed at about 1pm, i was hungry and needed to get something to eat. I decided to look for Mama Put.

My search was successful. I found a neat place, she had a variety of food to pick from, the food looked super delicious. It was a cool Saturday, so i decided to eat at her place, observe the environment and receive breeze rather than taking the food back home with me.

After devouring round one of the food, i looked up to ask Iya Tunde to "PUT" more food for me then i noticed an Aboki not far off "PATCHing" the clothes of one of his customers.

Then i said to myself, "What a scenario! A very good way to explain HTTP methods PUT and PATCH with their use cases while building APIs!!!"

# Introduction

HTTP methods are simply action words used to perform certain actions over HTTP. Most tutorials you'll find on the internet make use of four popular methods but there are more than four methods that could be used depending on the kind and functions of the API you want to build.

Sn | Method  | Meaning
-- | ------- | -------
1  | GET     | Fetch an existing resource from a host.
2  | POST    | Create a new resource on a host.
3  | PUT     | Replace a resource on a host with a new resource.
4  | DELETE  | Remove a resource on a host.
5  | PATCH   | Modify a resource on a host.
6  | OPTIONS | Specifies communication options for a resource on a host.
7  | HEAD    | Same as the GET method but it only sends back the Status and headers if access to the resource is successful.
8  | CONNECT | Establishes a tunnel to a host.
9  | TRACE   | Performs a message loopback test along the path to a target resource.

# Mama PUT
From the scenario in the inspiration for this post, I needed to replace the devoured food from the first round. 
This is the right use case for the PUT method. The PUT should be used when we want to update a resource (update the content of my plate like i was about to ask Iya Tunde to do). There are a couple of downside to using PUT to update a resource

- We would be asking clients to send the entire resource.
- Sending a complete resource representation utilizes more bandwidth.

**Example:**

```text
PUT /users/userId123

{
    "email": "user123@example.ng",
    "balance": 12000
}
```

# Aboki PATCH

From the scenario in the inspiration for this post, Before you give the Aboki your clothes to patch,
you need to describe and show him the area of the cloth to patch. This is also the way PATCH works. The biggest challenge with
this method is:

- Its usage misunderstood. 

The PATCH method requests that a set of changes, described in the request entity, must be applied to the resource identified by the request’s URI. This set contains instructions describing how a resource currently residing on the origin server should be modified to produce a new version.

**Wrong Example Usage 1:**

```text
PATCH /users/userId123

{ "balance": 10000 }
```

**Wrong Example Usage 2:**

```text
PATCH /users/userId123?balance=15000
```

**Correct Example Usage:**

```text
PATCH /users/userId123

[
    { "op": "replace", "path": "/balance", "value": 50000 }
]
```

# Some Questions

There have been some questions, confusion about PUT and PATCH.

- What on earth is *"Idempotence"*?
- Why isn't PATCH idempotent if it is a special case of PUT, which is idempotent?
- Why PATCH is not safe when compared to PUT or POST?


# Question 1

**What on earth is Idempotence?**

[restapitutorial.com](http://www.restapitutorial.com/) has done a great job in explaining what this is.

From a RESTful service standpoint, for an operation (or service call) to be idempotent,
clients can make that same call repeatedly while producing the same result.
In other words, making multiple identical requests has the same effect as
making a single request. Note that while idempotent operations produce
the same result on the server (no side effects), the response itself may
not be the same (e.g. a resource's state may change between requests).

The PUT and DELETE methods are defined to be idempotent. However, there is a caveat on DELETE. The problem with DELETE, which if successful would normally return a 200 (OK) or 204 (No Content), will often return a 404 (Not Found) on subsequent calls, unless the service is configured to "mark" resources for deletion without actually deleting them. However, when the service actually deletes the resource, the next call will not find the resource to delete it and return a 404. However, the state on the server is the same after each DELETE call, but the response is different.

GET, HEAD, OPTIONS and TRACE methods are defined as safe, meaning they are only intended for retrieving data. This makes them idempotent as well since multiple, identical requests will behave the same.

# Question 2

**Why isn’t PATCH idempotent if it is a special case of PUT, which is idempotent?**

A very simple answer would be because PUT contains a "new representation" of a resource, while PATCH contain "a set of changes" to a resource.

# Question 3

**Why PATCH is not safe when compared to PUT or POST?**

Safe in terms of REST refers to wether a method can modify a resource. From this meaning, neither PATCH, PUT, POST, DELETE or CONNECT is safe.
GET, HEAD and OPTIONS are safe.

# Extras

- Mozila Web **[Doc](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT)** on HTTP PUT
- Mozila Web **[Doc](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH)** on HTTP PATCH
- Indempotence in Cows and REST APIs **[on Youtube](https://www.youtube.com/watch?v=6dVNdFwqeKs)**

# Conclusion

I hope i have been able to show you the difference and use cases rather than 
confuse you about HTTP PUT and PATCH ✌✌✌✌✌✌✌✌✌✌

Also feel free to [Tweet at me](/), It would be a priviledge to chat with you.

Cheers!!!
