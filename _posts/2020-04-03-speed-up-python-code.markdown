---
layout: post
title: Speed up python code
date: 2020-04-03 05:58:57.000000000 +07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags: []
permalink: "/2020/04/03/speed-up-python-code/"
---

<https://towardsdatascience.com/how-to-speed-up-your-python-code-d31927691012>

I have read a few analyse in using python :

* Optimize your code first
* Use pypy library
* Use multithread for IO bound or asyncio
* Use multiprocess for CPU bound
* Use hadoop for distributed computing for move to cloud

One mark when we care about python, and this is ask in many job interview.
For IO bound application, we prefer multithread.
For CPU bound application, we prefer multiprocess.
