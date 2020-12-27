---
title: Remove Gem Version Specifiers
description: Make it easy to continuously keep your libraries up to date.
published_at: September 29, 2020 7 am PT
category: software
tags: rails joyful_rails
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of
recommendations to make developing your Rails app more productive and joyful.

In this article, we are talking about removing gem version specifiers.

## When

I recommend removing the gem version specifiers the first time you open the
Gemfile, i.e. at your earliest convenience.

I strongly recommend removing the gem version specifiers as soon as you believe
your project will be long-lived.

## Why

Gem version specifiers place restrictions on what versions of libraries (gems)
your app can use. They are useful for preventing gems from being changed to
a version that is incompatible with your app.

However, they also prevent you from updating gems on a regular and ongoing
basis. As a result, the gems in question will often not be updated until there
is a sudden need, for example a severe security vulnerability. And the longer a
gem has gone without update, the more difficult the update is likely to be.

You do not want to be stuck doing something very urgent and very difficult some
day.

You don't need gem version specifiers.

[Bundler](https://bundler.io) uses a lock file to make sure that your gem
versions don't change until you want them to. Your RSpec tests will make sure
that your code works perfectly with the updated gems when you do update them.

Remove the version specifiers from your gem file.

## How

Gem version specifiers show up as arguments to `gem` in your `Gemfile`.

For example in the line `gem 'puma', '~> 3.11'`, the version specifier is `'~>
3.11'`.

Remove these from your `Gemfile`.

Then run `bundle update` to upgrade to the latest version of all of your gems.

Make sure you run all of your tests so you know your application runs correctly
with your new gem versions.
