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
meta:
  _oembed_3a1fe40ce7a8432d3d3482882febcdea: "{{unknown}}"
  _oembed_0845b3fb439339aaa26d15536225d022: "{{unknown}}"
  _oembed_8d535614bbdf7ee0d57f8b046d311aaa: '<blockquote class="wp-embedded-content"
    data-secret="rPDTL8HDO5"><a href="https://eng.uber.com/michelangelo/">Meet Michelangelo:
    Uber&#8217;s Machine Learning Platform</a></blockquote><iframe class="wp-embedded-content"
    sandbox="allow-scripts" security="restricted" style="position: absolute; clip:
    rect(1px, 1px, 1px, 1px);" title="&#8220;Meet Michelangelo: Uber&#8217;s Machine
    Learning Platform&#8221; &#8212; Uber Engineering Blog" src="https://eng.uber.com/michelangelo/embed/#?secret=rPDTL8HDO5"
    data-secret="rPDTL8HDO5" width="500" height="282" frameborder="0" marginwidth="0"
    marginheight="0" scrolling="no"></iframe>'
  _oembed_time_8d535614bbdf7ee0d57f8b046d311aaa: '1581588750'
  _oembed_d61491834b4dee5987348783c8a406b3: "{{unknown}}"
  _oembed_afcaf258047a290663fcf0163429e107: "{{unknown}}"
  _oembed_522a0bf5b7caa95187b73bbb6ba14156: '<blockquote class="wp-embedded-content"
    data-secret="6a5b0LFXPN"><a href="https://eng.uber.com/michelangelo/">Meet Michelangelo:
    Uber&#8217;s Machine Learning Platform</a></blockquote><iframe class="wp-embedded-content"
    sandbox="allow-scripts" security="restricted" style="position: absolute; clip:
    rect(1px, 1px, 1px, 1px);" title="&#8220;Meet Michelangelo: Uber&#8217;s Machine
    Learning Platform&#8221; &#8212; Uber Engineering Blog" src="https://eng.uber.com/michelangelo/embed/#?secret=6a5b0LFXPN"
    data-secret="6a5b0LFXPN" width="420" height="237" frameborder="0" marginwidth="0"
    marginheight="0" scrolling="no"></iframe>'
  _oembed_869d127633fe20a6ca1e8f59b5a36674: "{{unknown}}"
  _oembed_bf2d354a1d93962628fdea67c411ad45: "{{unknown}}"
  _rest_api_published: '1'
  _rest_api_client_id: "-1"
  _publicize_job_id: '40641049919'
  _oembed_15962f252cb2a2d4f9293d1af94f0587: "{{unknown}}"
  _oembed_b423828691a35f6317ecd248082c17ff: "{{unknown}}"
  _oembed_time_522a0bf5b7caa95187b73bbb6ba14156: '1581588881'
  timeline_notification: '1581588882'
  _oembed_03b1a65f412d1d87c383c21edfd78734: "{{unknown}}"
  _oembed_3754b6d7d3cd9aebbf7a375cd6e18280: "{{unknown}}"
  _oembed_f47c11c683b7792cd6bafc863c2f2b40: "{{unknown}}"
  _oembed_c50637b36d80ba512ccd4d19749d0f41: '<blockquote class="wp-embedded-content"
    data-secret="wtU0ISxEBh"><a href="https://eng.uber.com/michelangelo/">Meet Michelangelo:
    Uber&#8217;s Machine Learning Platform</a></blockquote><iframe class="wp-embedded-content"
    sandbox="allow-scripts" security="restricted" style="position: absolute; clip:
    rect(1px, 1px, 1px, 1px);" title="&#8220;Meet Michelangelo: Uber&#8217;s Machine
    Learning Platform&#8221; &#8212; Uber Engineering Blog" src="https://eng.uber.com/michelangelo/embed/#?secret=wtU0ISxEBh"
    data-secret="wtU0ISxEBh" width="600" height="338" frameborder="0" marginwidth="0"
    marginheight="0" scrolling="no"></iframe>'
  _oembed_time_c50637b36d80ba512ccd4d19749d0f41: '1581588886'
  _oembed_ddbc8bf4a4191b03653e23298d7622de: "{{unknown}}"

permalink: "/2020/02/13/ai-model-deployment/"
---
<ol>
<li>Create queue services:</li>
</ol>
<p>Create a queue service including 3 task:</p>
<ul>
<li>Add job to queue</li>
<li>Check job status</li>
<li>Process job</li>
</ul>
<p>Using MLQ</p>
<p>https://towardsdatascience.com/there-are-two-very-different-ways-to-deploy-ml-models-heres-both-ce2e97c7b9b1</p>
<p>Try to use CICD to increase deployment :</p>
<p><img src="{{ site.baseurl }}/assets/6987e-1bit0ilfcx9ntpgxo7fxwtw.png" /></p>
<p>&nbsp;</p>
<p>2. Alternatives:</p>
<p>Combine</p>
<p>https://github.com/tensorflow/serving</p>
<p>https://opensource.googleblog.com/2016/02/running-your-models-in-production-with.html</p>
<p>Tensorflow Serving, it is opensource, so we could serve ourselves for model prediction.</p>
<p>https://eng.uber.com/michelangelo/</p>
<p><img src="{{ site.baseurl }}/assets/image8.png" /></p>
<p>A development and deployment model from Michelangelo Uber.</p>
<p>https://blog.usejournal.com/a-guide-to-deploying-machine-deep-learning-model-s-in-production-e497fd4b734a</p>
<p>&nbsp;</p>
