---
title: Use a Ruby Linter
description: Make your Ruby style consistent.
published_at: November 17, 2020 7 am PT
category: software
tags: rails joyful_rails
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of recommendations to make
developing your Rails app more productive and joyful.

In this article, we are talking about using a Ruby linter.

## When

The longer you wait to add a Ruby linter, the more work you will have to correct
style errors that have accumulated. For that reason, I recommend adding a
linter, such as RuboCop, as early as possible.

## Why

Having a consistent style makes code easier to read and maintain. Using a
linter makes it easy to conform to a consistent style. In a lot of cases, your
linter can make corrections automatically.

## How

1. Add the RuboCop gem. Add the `gem 'rubocop'` to the development group
   of your `Gemfile` and run `bundle`.
2. Configure RuboCop. Add a `.rubocop.yml` with the RuboCop configuration.
3. Run RuboCop with auto-correct, `rubocop --auto-correct`.
4. Correct errors that RuboCop cannot correct automatically.

<!-- Add section with link to my Rubocop config -->
