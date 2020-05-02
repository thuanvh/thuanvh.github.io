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
meta:
  _oembed_1c4a33e820fcab9a2ebc3d101e695931: "{{unknown}}"
  _oembed_ec49722112c56317ee1e212f40ede15f: "{{unknown}}"
  _oembed_93d0b28b76b1e6fb5e07f4ccc0ddd5b8: "{{unknown}}"
  _oembed_6b35f87f004ae587b3a6128eb02851d9: "{{unknown}}"
  _oembed_8d95da8111f599b1a566c97587e9524a: "{{unknown}}"
  _oembed_59b1d54b64ad8eec4e0e4245e08ca558: "{{unknown}}"
  _oembed_77d6d2ec7896da2af2f714a980e26519: "{{unknown}}"
  _wp_old_date: '2019-10-18'
  _rest_api_published: '1'
  _rest_api_client_id: "-1"
  _publicize_job_id: '42336032053'
  timeline_notification: '1585413995'

permalink: "/2020/03/28/training-parallelism/"
---
<p><strong>Training with memory limit</strong></p>
<p>One of interesting test about training with memory limit. He use the way to store some nodes in forward steps (not all nodes). Then in backward steps, he recalculate some forward steps (which is not stored) for gradient calculation. The nodes indexes which are stored are sqrt(i)-th node.</p>
<p><a href="https://github.com/cybertronai/gradient-checkpointing">https://github.com/cybertronai/gradient-checkpointing<br />
</a><br />
And he wrote a post about this technique:</p>
<p><a href="https://medium.com/tensorflow/fitting-larger-networks-into-memory-583e3c758ff9">https://medium.com/tensorflow/fitting-larger-networks-into-memory-583e3c758ff9</a></p>
<p>And the checkpoint concept is used in PyTorch also. The same concept with the above idea. It will save results of some activation nodes. And the other will be recalculated in backward processing.</p>
<p><a href="https://pytorch.org/docs/stable/checkpoint.html">https://pytorch.org/docs/stable/checkpoint.html</a></p>
<p>Normally, with big deeplearning model, with limit memory of GPU, we must train 1 by 1 sample per step. So the gradient is quite noisy. One technique used in this case is gradient-average (Accumulating gradients)</p>
<p>https://gchlebus.github.io/2018/06/05/gradient-averaging.html</p>
<p>&nbsp;</p>
