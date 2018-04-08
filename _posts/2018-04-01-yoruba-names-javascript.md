---
title: "Yoruba-Names"
layout: post
date: 2018-04-01 16:30
tag: 
    - javascript
    - yoruba-names
    - git
    - github
    - nodejs
    - mocha
    - travis-ci
    - webpack
    - es6
    - npm
image: false
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "Get a random yoruba name"
category: project
author: lagosnomad
externalLink: false
---

![Screenshot](../assets/images/projects/ynjs.png)
Yoruba-Names is an opensource micro javascript library . And before you ask: It's GNU 3.0 licensed!

---

# Easy to setup

{% highlight sh %}
npm install --save yoruba-names
{% endhighlight %}

# Easy to use

{% highlight javascript %}
var yorubaNames = require('yoruba-names');

// Get a random Yoruba name
console.log(yorubaNames.random());

// Get a random number of Yoruba names
console.log(yorubaNames.random(2));

// Get a random Yoruba fullname
console.log(yorubaNames.random() + " " + yorubaNames.random());
{% endhighlight %}

# Wow even in our browsers

{% highlight html %}
<html>

<head>
    <script src="https://unpkg.com/yoruba-names@2.2.0/dist/index.umd.min.js" type="text/javascript"></script>
</head>

<body>
    <button onclick="document.write(yorubaNames.random())">Get a random name</button>
    <button onclick="document.write(yorubaNames.random(4))">Get a random number of names</button>
</body>

</html>
{% endhighlight %}

---

# Contribute

Found a bug? Have a good idea for improving Yoruba-Names? Head over to [the github page](https://github.com/mczlatan/yoruba-names) and create a new ticket or fork. 
You can also directly add issues and feature requests to the issue tracker.
If you just want to chat with me, my twitter is [here](/)