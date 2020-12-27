---
title: Switch to RSpec
description: Use a clear and expressive testing framework.
published_at: October 20, 2020 7 am PT
category: software
tags: rails joyful_rails
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of
recommendations to make developing your Rails app more productive and joyful.

In this article, we are talking about switching to RSpec.

## When

I recommend making the switch before writing any specifications.

## Why

[RSpec](https://rspec.info) makes it easier and more pleasant to write
executable specifications for Ruby.

## How

1. Install Rspec. Add `rspec-rails` to the `Gemfile` in the test group and run
`bundle`.
2. Generate Rspec boilerplate. Run `rails generate rspec:install`.
3. Configure generators to generate rspec tests. Add
`config.generators.test_framework = :rspec` to `config/application.rb`.
4. Remove fixtures. In `spec/rails_helper.rb` remove the line starting with
`config.fixture_path = `.
4. Remove minitest boilerplate. `git rm -r test/`.
5. Make a commit

Test that this works by running `rails generate model foo`.

You should get a migration, a model file, and an RSpec spec file for the model.
You should not get any Minitest files. RSpec (`rspec`) should run successfully.

Remove the files created by the generator.
