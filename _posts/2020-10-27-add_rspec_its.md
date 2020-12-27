---
title: Add RSpec::Its
description: Make it easier to test object attributes.
published_at: October 27, 2020 7am PT
category: software
tags: [rails]
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of
recommendations to make developing your Rails app more productive and joyful.

In this article, we are talking about adding RSpec::Its.

## When

Add [Rspec::Its](https://github.com/rspec/rspec-its) when you want to make
it easier to test the attributes of an object.

## Why

With RSpec::Its you can write

```ruby
its(:size) { is_expected.to eq(1) }
```

instead of

```ruby
specify { expect(subject.size).to eq(1) }
```

## How

Add `rspec-its` to the `Gemfile` in the test group and run `bundle`.
