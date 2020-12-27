---
title: Add Authentication
description: Identify your users.
published_at: February 2, 2021 7 am PT
category: software
tags: [rails]
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of recommendations to make
developing your Rails app more productive and joyful.

In this article, we are talking about adding authentication.

## When

Authentication is the process of identifying who your user is. You should add it
as soon as your app needs to know who its users are.

## How

Use [Devise](https://github.com/heartcombo/devise#getting-started).

## Gotchas

Authentication is separate from authorization. We'll talk about authorization in
a separate article.
