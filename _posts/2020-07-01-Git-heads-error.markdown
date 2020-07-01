---
layout : post
---
Git error when we have only 1 branch and reference it to only 1 branch.

We run git fetch but nothing is updated.
So must update fetch configuration.

```
> git config --get remote.origin.fetch
+refs/heads/develop:refs/remotes/origin/develop

> git config remote.origin.fetch "+refs/heads/*:refs/remotes/origin/*"

> git config --get remote.origin.fetch
+refs/heads/*:refs/remotes/origin/*

```