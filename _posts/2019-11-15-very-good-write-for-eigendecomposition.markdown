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

permalink: "/2019/11/15/very-good-write-for-eigendecomposition/"
---

In the deep learning book written by Ian Goodfellow and Yoshua Bengio and Aaron Courville.

<http://www.deeplearningbook.org/contents/linear_algebra.html>

They have a good description about eigen decomposition.

# Eigen Decomposition
```
One of the most widely used kinds of matrix decomposition is called 
eigen-decomposition, 
in which we decompose a matrix into a set of eigenvectors and eigenvalues.
An eigenvector of a square matrix A is a nonzero vector v such that 
multiplication by 
A  alters only the scale of v:Av = λv. (2.39)  .
The scalar λ is known as the eigenvalue corresponding to this eigenvector.
 (One can also ﬁnd a left eigenvector such that vA=λv, 
 but we are usually concerned with right eigenvectors.)

```

# SVD (p.42)
```
The singular value decomposition (SVD) provides another way to 
factorize a matrix, 
into *singular vectors* and *singular values*. The SVD enables us to
discover some of the same kind of information as the eigen 
decomposition reveals;
however, the SVD is more generally applicable. Every real 
matrix has a singular
value decomposition, but the same is not true of 
the eigenvalue decomposition.

For example, if a matrix is not square, the eigendecomposition 
is not deﬁned, and
we must use a singular value decomposition instead.
```