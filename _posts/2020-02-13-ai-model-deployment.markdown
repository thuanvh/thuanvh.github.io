---
layout: post
title: AI Model deployment
date: 2020-02-13 10:14:37.000000000 +07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags: []
permalink: "/2020/02/13/ai-model-deployment/"
---
# Create queue services:

Create a queue service including 3 task:
* Add job to queue

First query is just register a job. The job will be added into a queue in server.
* Check job status

Client will frequently check status of the registered job.
* Process job

Server will process jobs, when a job is finished. Client will do next step.


# Using MLQ

<https://towardsdatascience.com/there-are-two-very-different-ways-to-deploy-ml-models-heres-both-ce2e97c7b9b1>

Try to use CICD to increase deployment :

<img src="/assets/6987e-1bit0ilfcx9ntpgxo7fxwtw.png" />



# Alternatives:

Combine

<https://github.com/tensorflow/serving>

<https://opensource.googleblog.com/2016/02/running-your-models-in-production-with.html>

Tensorflow Serving, it is opensource, so we could serve ourselves for model prediction.

<https://eng.uber.com/michelangelo>

<img src="/assets/image8.png" />

A development and deployment model from Michelangelo Uber.

<https://blog.usejournal.com/a-guide-to-deploying-machine-deep-learning-model-s-in-production-e497fd4b734a>


