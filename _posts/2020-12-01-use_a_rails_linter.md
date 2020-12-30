---
title: Use a Rails Linter
description: Avoid common Rails mistakes and correct them automatically.
published_at: December 1, 2020 7 am PT
category: software
tags: rails joyful_rails
---

{% include joyful-rails-intro.html %}

In this article, we are talking about using a Rails linter. 

## When

The longer you wait to add a linter, the more work you will have to correct
style errors that have accumulated. For that reason, I recommend adding a Rails
linter as early as possible.

## Why

A Rails linter like the [Rails Best Practices
gem](https://github.com/flyerhzm/rails_best_practices) can catch and sometimes
correct common mistakes and problems in Rails code.

## How

To install, add `rails_best_practices` to the development section of your
Gemfile.

To run, use the command `rails_best_practices .`

<!-- Add section with link to default rake -->
