---
title: "Rest In Peace"
layout: post
date: 2016-12-26 
tag: 
    - REST
    - API
    - SOAP
    - XML
    - JSON
image: /assets/images/post-bg-02.jpg
headerImage: false
projects: false
hidden: false # don't count this post in blog pagination
description: "Understanding the concepts of REST without dying first."
category: blog
author: lagosnomad
externalLink: false
---
![Rest In Peace](../assets/images/post-bg-02.jpg)


<h2 class="section-heading">Yet another concept.</h2>


```
ME: Arrgh! There are so many programming concepts to learn, 
    I don't think i can do this! I think i need to REST.
```

<p>When i started off with development, I got to a stage where i needed to present layers of information 
    to enable me build other little clients on top of this data.
    The trad way would be to build this smaller clients on top of the same database, something like building
    facebook off a set of data, and also building twitter off that same set of data.
    Yes it would work but deep down i knew it wasn't efficient and didn't cut to the chase quick and well enough.
    So i did what we would all do, Google.
</p>

<p>I think it took me less than a minute to discover something called an API.
    Whaaaaaat!!! Another programming concept i have to understand? like spending a full week understanding how
    polymorphism and abstraction  works wasn't enough???. It took a while to fully grasp the concept, say two days of
    consistent reading, even when i go to "dump data" in the toilet, or helping out my mum in the kitchen(Yes i cook...very well).
</p>

<p>So, what i would be writing about today is how to understand API and one of the major
    trends in API called REST in peace without you dying first. So below are some topics i would try to cover.
</p>

``` text
1- What is an API?
2- RESTlessness (aka SOAP)
3- RESTfulness
```

### 1- What is an API?

<p>An API is an acronym and it stands for Application Programming Interface.
    To easily understand it, see an API as an interface to some underlying data that you can program applications on top.<br>
    You see, very easy - an interface to some underlying data that you can program applications on top.<br>
    And this "interface" usually comes with some sort of document telling you what you can do on top of this interface.
    This document is called the API Documentation.
    This is all you have to know basically about what an API is.
</p>

### 2- RESTlessness (aka SOAP)
<p>
    <ul>
        <li>It is an acronym for Simple Object Access Protocol.</li>
        <li>It is somewhat a defacto for sharing data across enterprise systems in enterprise organizations.</li>
        <li>It is designed for distributed systems.</li>
        <li>It uses XML.</li>
        <li>It so old, jeez.</li>
        <li>But many IDEs support SOAP development.</li>
    </ul>
    So, that's basically what you need to know about SOAP. I'm trying my best to keep it simple and stay away from some technical
    terms. But once you understand these basics, you can always learn more complex stuff. The concept would still
    stick in your head and the complex stuffs will all start to make sense.
</p>

### 3- RESTfulness
<p>
    <ul>
        <li>It is an acronym for Representational State Transfer.</li>
        <li>It is somewhat a defacto for building APIs these days.</li>
        <li>It's lightweight. You really don't have to bother about bandwidth.</li>
        <li>It uses Json as defacto and XML for data representation.</li>
        <li>REST is safe.</li>
        <li>Almost any client(terminal, mobile apps, web browser,etc) can consume(use or act on) REST data.</li>
        <li>You can even use it to expose data over the internet.</li>
        <li>It's the new cool kid on the block and everyone is using it. eg Facebook, Twitter, etc.</li>
    </ul>
    That's basically what you need to know about REST. And like i said once you understand these basics, you can always learn more complex stuff. The concept would still
    stick in your head and complex the stuffs will all start to make sense.
</p>


<p>I'm currently working on a simple REST API project - this will cover a lot of topics in implementation such as
    validation, expiration, authentication, etc. I'll talk about my challenges and how i fixed them in some other
    post and show you my implementation.<br><br>

    Just incase there's anything i left out, missed or anything, leave me a message on my <a href="/">Twitter</a>
    and I'll include, correct, or ackwnowledge it.<br><br>
    Merry Christmas, Happy Boxing Day and a very prosperous new year in advance.<br>
</p>