---
title: Ruby Version Management
description: Use the right version of Ruby for the job.
published_at: August 4, 2020 7 am PT
category: software
tags: [rails]
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of
recommendations to make developing your Rails app more productive and joyful.

In this article, we are talking about Ruby version management.

## When

A Ruby version manager is helpful when you want to easily switch to a different
version of Ruby, either to get new features or to work on different projects.

## Why

The Ruby runtime included by default on your machine is probably not the one
you want to use. The default Ruby on MacOS requires root privileges to install
gems and tends to lag far behind the current Ruby version.

Also, your different Ruby projects may use different Ruby versions.

## What

[RVM](https://rvm.io), aka the Ruby Version Manager, manages multiple versions
of Ruby and its libraries (called gems).

## How

To [install](https://rvm.io/rvm/install#any-other-system) RVM, run this command:

```sh
\curl -sSL https://get.rvm.io | bash -s stable
```

If you already have RVM, update it with `rvm get`.

To switch Ruby version, run `rvm use ruby-<version_number>`. You can see the
latest Ruby version on the [Ruby website](https://www.ruby-lang.org/en/).

## Alternatives

[rbenv](https://github.com/rbenv/rbenv) is another (possibly
[better](https://github.com/rbenv/rbenv/wiki/Why-rbenv%3F)) option.
