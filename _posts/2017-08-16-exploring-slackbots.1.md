---
title: "Rise of the Machines - 1"
description: "Exploring Slackbots"
image: /assets/images/post-bg-08.jpg
tag: 
    - slack
    - slackbot
    - microsoft
    - bots
    - robots
    - tay
    - github
    - stackify
    - gitify
    - python
    - pip
    - heroku
author: lagosnomad
category: tours
layout: post
headerImage: false
projects: false
tours: true
hidden: false # don't count this post in blog pagination
externalLink: false
date: 2017-08-16
---
![Rise of the Machines](../assets/images/post-bg-08.jpg)

# Are bots really the future?

``` txt
Microsoft made a teenage bot called Tay that ended up tweeting 
racist and offensive messages.
```

[Follow Tay](https://twitter.com/tayandyou) on twitter.

I've always wondered about bots and the dark magic behind them and have always wanted to write one,
even if the only thing it could do was say "Hello World!".
Apprently, bots are just:

- A simple program that does automated tasks (in-app cron jobs???).
- They come in different types: Good bots, bad bots, ugly bots, chat bots, robots, this bot, that bot, etc bots.
- and any other interesting stuff you find about bots out there.

# Slack Bots

These days, I spend a lot of time on slack, just after whatsapp and twitter. 
Apart fro slack being a great place to manage a team or community, the adoption of bots have made that very interesting.
Currently I'm in 19 open slack communities. This has been a great way to learn new things, share problems, keep up to date
with the technologies I use, meet new people, etc.

Recently, there was a need for me to create and start managing an open community. and i saw this as a perfect chance to venture
into buillding bots starting with Slackbots.

## Getting started

I won't be going into technical details, just a summary of how i was able to build my first 
slack bot and went ahead to build two other useful and real life applicable slack bots, Stackify nd Gitify Slack Bots.
I'll bulletify the summary just because i like the sound of "ify".

- I googled "building your first slack bot".
- I discovered there were two popular way of building bots, using NodeJS and Python.
- Also there were different ways of deploying your bot. Two popular way is to use [Heroku](https://heroku.com) or self host them.
- I decided to use python because i've been writing python longer than NodeJS.
- I followed [a tutorial from Fullstack Python](https://www.fullstackpython.com/blog/build-first-slack-bot-python.html).
- I self hosted it and tested it in the slack community i was building.
- And that was how i build my first slack bot.

### [Stackify Slackbot](https://github.com/mczlatan/stackify-slackbot)

This slack bot helps you to search Stack Overflow for matching answers to your issues.
E.g to search for answers relating to "Broken pipe error" in Java, you would do:

```txt
@stackify search null pointer error [java]
```

How i achieved it:

- Python.
- Python urllib.
- Python Slackclient.
- Some Stack Overflow URL manipulations.

I self hosted this bot for the community and you can [find it here](https://github.com/mczlatan/stackify-slackbot) and also deploy it for your community.

### [Gitify Slackbot](https://github.com/mczlatan/gitify-slackbot)

This slack bot helps you to search github for users, repositories, codes, issues, and wikis.
E.g to search for anything on me on github:

```txt
@gitify search mczlatan
```

The above will send a json response with links to wikis, users, repos, codes, etc.
It can still be optimized to search  for just one catergory.
How i achieved it:

- Python.
- Python json.
- Python urllib.
- Python Slackclient.
- Some Github URL manipulations.

I self hosted this bot for the community and you can [find it here](https://github.com/mczlatan/gitify-slackbot) and also deploy it for your community.

# Development

Want to contribute? Great!
Fork the projects, send in a pull request.

Cheers!!!
