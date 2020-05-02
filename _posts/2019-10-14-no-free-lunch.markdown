---
layout: post
title: No free lunch
date: 2019-10-14 08:48:29.000000000 +07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags: []
meta:
  _oembed_29cf72aa57e35465d944c199188ff86a: <div class="embed-reddit">    <blockquote
    class="reddit-card" >      <a href="https://www.reddit.com/r/golang/comments/di3n1k/the_pigo_face_detection_library_now_is_capable/?ref_source=embed&amp;ref=share">The
    Pigo face detection library now is capable for facial landmark points detection</a>
    from      <a href="https://www.reddit.com/r/golang/">golang</a>    </blockquote>    <script
    async src="https://embed.redditmedia.com/widgets/platform.js" charset="UTF-8"></script></div>
  _oembed_time_29cf72aa57e35465d944c199188ff86a: '1571217366'

permalink: "/2019/10/14/no-free-lunch/"
---

Today, I luckily have read a post about No Free Lunch for Data Science. In the meaning, there are no free lunch for any algorithms, any models, any search algorithm in our world.

https://www.kdnuggets.com/2019/09/no-free-lunch-data-science.html

I resumed some ideas :
<ul>
<li>No perfect, completely perfect machine learning algorithm, supervised algorithm. It only is good in context of some dataset. But another context it maybe not. We not sure.</li>
<li>It is right for search algorithms in case of large search space.</li>
<li>Revive me 2 concepts: priori and posteriori. Priori is knowledge about truth without the current state of the world. Posteriori is knowledge base on observation in the world.</li>
<li>Some class of family machine learning method give best result in alot of dataset: such as Random Forest, SVM, boosting, neural networks. =&gt; There a top of machine learning methods are in top of Kaggle and in production. But we must keep in mind that NO FREE LUNCH. These methods maybe not working well in some cases.</li>
<li> To avoid No Free Lunch consequence:
<ul>
<li>We must aware of some assumptions before relying on model or search algorithm.</li>
<li>Keep in mind about No perfect algorithms for all dataset</li>
<li>Keep improving</li>
</ul>
</li>
</ul>
