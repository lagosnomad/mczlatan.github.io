---
title: "Captain Freeze"
description: "Updating all your Python packages like a boss 😎"
image: /assets/images/post-bg-14.jpg
tag: 
    - python
    - security
    - hacker
    - pip
    - pypi
    - freeze
    - malware
author: lagosnomad
category: blog
layout: post
headerImage: false
projects: false
hidden: false # don't count this post in blog pagination
externalLink: false
date: 2017-10-27
---
![Captain Freeze](../assets/images/post-bg-14.jpg)

If you still use Python 2.7, let me see your hands up 👋. Don't be shy about it. [Python Clock](https://pythonclock.org/) shows a count down to an assumed date when Python 2.7 will no longer be maintained. Time to start embracing Python 3.x.

# Do you agree?

Python is a great language, useful in many ways, it has a large community, lots and lots of libraries, easy to use package manager, etc, etc.

As time goes by and you work on different projects, you end up installing so many packages. Some of these pakages maybe used accross different projects, and some you'll never use again.

## The Concern

**Security**

Last month, [10 Malicious packages were found on PYPI](https://www.bleepingcomputer.com/news/security/ten-malicious-libraries-found-on-pypi-python-package-index/). I'm not sure how many of us out there heard of this news. Just to be sure you are safe, you might want to run the command below and if any of the packages are found, you should uninstall them and reinstall the original package:

```bash
pip freeze | grep 'acqusition\|apidev-coop\|bzip\|crypt\|django-server\|pwd\|setup-tools\|telnet\|urlib3\|urllib' | grep -v 'acquisition\|apidev-coop_cms\|bz2file\|crypto\|django-server-guardian-api\|pwdhash\|setuptools\|telnetsrvlib\|urllib3'
```

Security breaches come in many forms. Most exploits are usually carried out on outdated softwares (well except for zero days). This made me realize that I had a lot of outdated packages and this means I was open to vulnerabilities and I also lacked bug fixes and new features in libraries I had installed.

## Updating like a boss 😎

```bash
python -c 'import pip, subprocess; [subprocess.call("pip install -U " + package.project_name, shell=1) for package in pip.get_installed_distributions()]'
```

**SPOILER:** understanding list comprehension is needed to understand the command above.

- ```-c``` argument which allows you pass in small valid python codes as a string from your terminal
- ```for package in pip.get_installed_distributions()``` iterates over every of your installed packages, and for every ```package```, it appends the package name ```package.project_name``` to the ```pip install -U ``` command.
- ```subprocess.call()``` is a function defined in the subprocess package and what it does is to take commands run them like it's from your terminal.

# In conclusion

Always keep your libraries, softwares, and operating systems up to date.

Yea, [keep your self updated too by following me on twitter](/). I tweet and retweet about the latest dev and sec stuffs.

Cheers!!! ✌✌✌
