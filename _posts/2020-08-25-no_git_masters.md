---
title: No Git Masters
description: Remove problematic language from your Git setup.
published_at: August 25, 2020 7 am PT
category: software
tags: rails joyful_rails
---

{% include joyful-rails-intro.html %}

In this article, we are talking about Git default branch names.

## Why

In Git, the default branch name is `master`. This term should be avoided because
of its connection to slavery. It also does not clearly or accurately describe
the default branch.

## How

Create a new branch with the new name, "develop".

`git checkout -b develop`

Push the develop branch up to your remote git repository.

`git push origin develop`

Delete the master branch.

`git branch --delete --force master`

Make the develop branch the default branch. On GitHub you can do that under
Settings -> Branches.

Delete the master branch on your remote repository.

`git push origin --delete master`

## Alternatives

In the example, we used the name `develop`. Other good options are `main` and
`development`.
