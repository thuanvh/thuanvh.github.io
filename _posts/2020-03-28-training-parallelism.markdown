---
layout: post
title: Training Parallelism
date: 2020-03-28 16:46:30.000000000 +07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags: []

permalink: "/2020/03/28/training-parallelism/"
---

# Training with memory limit

One of interesting test about training with memory limit. He use the way to store some nodes in forward steps (not all nodes). Then in backward steps, he recalculate some forward steps (which is not stored) for gradient calculation. The nodes indexes which are stored are sqrt(i)-th node.

<https://github.com/cybertronai/gradient-checkpointing>

And he wrote a post about this technique:

<https://medium.com/tensorflow/fitting-larger-networks-into-memory-583e3c758ff9>

And the checkpoint concept is used in PyTorch also. The same concept with the above idea. It will save results of some activation nodes. And the other will be recalculated in backward processing.

<https://pytorch.org/docs/stable/checkpoint.html>

Normally, with big deeplearning model, with limit memory of GPU, we must train 1 by 1 sample per step. So the gradient is quite noisy. One technique used in this case is gradient-average (Accumulating gradients)

<https://gchlebus.github.io/2018/06/05/gradient-averaging.html>


