---
layout: post
title: Very good write for eigendecomposition
date: 2019-11-15 09:27:12.000000000 +07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags: []
meta:
  _oembed_753e81b64b8be7b20e914707a530b4f6: "{{unknown}}"
  _oembed_fcbbd28dd394029403fb7110479dfd08: "{{unknown}}"
  timeline_notification: '1573810034'
  _rest_api_published: '1'
  _rest_api_client_id: "-1"
  _publicize_job_id: '37445936901'
  _oembed_09efd78c7225b8a247ad90b2c86eec61: "{{unknown}}"

permalink: "/2019/11/15/very-good-write-for-eigendecomposition/"
---
<p>http://www.deeplearningbook.org/contents/linear_algebra.html</p>
<p>Eigen Decomposition</p>
<blockquote>
<div>
<div class="t m2 x1 h3 y1de ff3 fs2 fc0 sc0 ls0 ws0">One of the most widely used kinds of matrix decomposition is called eigen-decomposition, in which we decompose a matrix into a set of eigenvectors and</div>
<div class="t m0 x0 h3 y1e0 ff3 fs2 fc0 sc0 ls0 ws0">eigenvalues.</div>
<div class="t m17 x1 h3 y9c ff3 fs2 fc0 sc0 ls0 ws0">An eigenvector of a square matrix A is a nonzero vector v such that multiplication by <span class="ffb">A </span>alters only the scale of <span class="ffb">v</span>:</div>
<div class="t m0 x56 h3 y1e1 ffb fs2 fc0 sc0 ls0 ws0">Av <span class="ffe">= <span class="ff9">λ</span></span>v<span class="ff9">. <span class="ff3">(2.39)</span></span></div>
<div class="t mf x5 h3 y1e2 ff3 fs2 fc0 sc0 ls0 ws0">The scalar λ is known as the eigenvalue corresponding to this eigenvector. (One can also ﬁnd a left eigenvector such that vA=λ<span class="ffb">v</span>, but we are usually concerned with right eigenvectors.)</div>
</div>
</blockquote>
<div class="t mf x5 h3 y1e2 ff3 fs2 fc0 sc0 ls0 ws0">SVD (p.42)</div>
<div></div>
<blockquote>
<div id="pfe" class="pf w0 h0">
<div class="pc pce w0 h0 opened">
<div class="t m2 x5 h3 y245 ff3 fs2 fc0 sc0 ls0 ws0">The singular value decomposition (SVD) provides another way to factorize a matrix, into <strong>singular vectors</strong> and <strong>singular values</strong>. The SVD enables us to</div>
<div class="t m5 x0 h3 y247 ff3 fs2 fc0 sc0 ls0 ws0">discover some of the same kind of information as the eigendecomposition reveals;</div>
<div class="t m12 x0 h3 y248 ff3 fs2 fc0 sc0 ls0 ws0">however, the SVD is more generally applicable. Every real matrix has a singular</div>
<div class="t m2 x5 h3 y249 ff3 fs2 fc0 sc0 ls0 ws0">value decomposition, but the same is not true of the eigenvalue decomposition.</div>
</div>
</div>
<div id="pff" class="pf w0 h0">
<div class="pc pcf w0 h0 opened">
<div class="t m6 x0 h3 y1a ff3 fs2 fc0 sc0 ls0 ws0">For example, if a matrix is not square, the eigendecomposition is not deﬁned, and</div>
<div class="t m0 x5 h3 y1b ff3 fs2 fc0 sc0 ls0 ws0">we must use a singular value decomposition instead.</div>
</div>
</div>
</blockquote>
