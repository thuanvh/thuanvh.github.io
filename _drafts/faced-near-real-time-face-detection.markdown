---
layout: post
title: Faced - near real-time face detection
date: 
type: post
parent_id: '0'
published: false
password: ''
status: draft
categories: []
tags: []
meta:
  _oembed_42cf1c32a6a8123d996d685812a525a3: "{{unknown}}"

permalink: "/"
---

It is a combination of Yolo and Full-DCNN

Yolo for create a grid 9x9 rectangle for detection.

Full-DCNN for fine-tuning which face rectangles in the above grid.

https://github.com/iitzco/faced

One notice marked in this repos. That means Yolo is currently
<blockquote>
[1] Those models cannot perform Real Time on CPU (YOLO at least). Even tiny-yolo version cannot achieve 1 fps on CPU (tested on 2015 MacBook Pro with 2.6 GHz Intel Core i5).</blockquote>
