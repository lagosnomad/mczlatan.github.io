---
title: "Reverse Engineering Hybrid Mobile Apps - For Fun and Profit (Part 1)"
description: "Hacking and securing hybrid mobile apps."
image: /assets/images/post-bg-10.jpg
tag: 
    - javascript
    - ionic
    - cordova
    - hybrid
    - android
    - ios
    - app
    - mobile
    - hacker
author: lagosnomad
category: blog
layout: post
headerImage: false
projects: false
hidden: false # don't count this post in blog pagination
externalLink: false
date: 2018-04-19
---
![Reverse Engineering Hybrid Apps](../assets/images/post-bg-17.jpeg)

Whenever you plan to develop a mobile app, there are usually two approaches to choose from:
- The native way 
- The hybrid way
Each approach has its own pros and cons depending on the features of what you're building, your budget, 
project timeline, user experience, present and future maintenance, and the skills and number of your developers.

## Hybrid Mobile Apps
A high level description of an hybrid mobile is a webview running inside a native container. Your application code is bundled into a webview and rendered in a native container on a mobile phone. 

Simply explaining, Hybrid applications allow you to write your application code in your already familiar web languages - HTML, CSS, Javascript and compile them together to give you a mobile app that will run on any mobile platform - iOS, Android, Blackberry, Windows, etc.

[Upwork](https://www.upwork.com), a freelancer website has a very good explanation on what hybrid mobile app are and how they work.

## Some Pros of Hybrid Mobile Apps
- **It's cross-platfrom:**
    - You only one codebase for all platforms - iOS, Android, Blackberry, Windows, etc.
- **Learning curve is easy:** 
    - Since you can leverage on exixting web technology skills.
- **You save time and money:**
    - You don't have to pay developers to build for different platforms and therefore directly reduce the time spent developing the app.
- **Scaling is easy:**
    - Once you build for a platform, you basically just have to compile again for another platform and that's it.
- **Native Features:**
    - You still have access to the underlying features of the mobile device like camera, touchid, vibration, etc. There are plugins/library that enable this. 

## Some Cons of Hybrid Mobile Apps
- **Performance**
    - This is the biggest drawback of hybrid apps. They can be slow and irresponsive. Since they run in a webview they are only as good as the webview they run in.
- **User Exxperience**
    - Hybrid applications look and feel different from native apps. Yes, because they run in a webview.
- **Security**
    - Hybrid applications are not secure. They can easily be re-engineered and most developers don't go the extra mile to secure the application.


### Conclusion
We now have a basic understanding of what Hybrid appications are and how they work and can proceed to reverse engineering them in the part 2.
 
I'll be using a demo application i built in my [previous blog post here](/out-of-boredom-series/), you can download the application [.apk file here.](https://drive.google.com/file/d/0B0bPh_TFeiUZbFZjdndHcFJBRlE/view) and we can dive into action in the part 2.

Also feel free to [Tweet at me](/), It would be a priviledge to chat with you.

Cheers!!!
 




