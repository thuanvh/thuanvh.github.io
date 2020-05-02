---
layout: post
title: Note of compare vector ptr and obj
date: 2020-03-24 03:28:22.000000000 +07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags: []
meta:
  _rest_api_published: '1'
  _rest_api_client_id: "-1"
  _publicize_job_id: '42147658760'
  timeline_notification: '1585020506'

permalink: "/2020/03/24/note-of-compare-vector-ptr-and-obj/"
---

Blog: https://www.bfilipek.com/2014/05/vector-of-objects-vs-vector-of-pointers.html

Source: https://github.com/fenbf/PointerAccessTest

Benchmark: http://quick-bench.com/VtyucjvZtTHo0czC96LARyWg_VU

In this blog post, the author Bartlomiej Filipek wrote about the difference of vector of ptr and obj in two operations of updating and sorting.

In updating, vector of object give a better performance than pointer. Because of when processing ptr, the memory of data is located somewhere rather than in a continuous memory of vector of object.

And in sorting, sorting of ptr is faster. Because of moving object (swap) inside of vector is heavier than ptr.

One good think is I could see a QuickBench which is used to create a fast benchmark to check code faster. It is very interesting tool. http://quick-bench.com/

QuickBench uses Google benchmark library https://github.com/google/benchmark




