---
title: Update the Readme
description: What do future developers need to know? What do you need to tell them?
published_at: January 26, 2021 7 am PT
category: software
tags: rails joyful_rails
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of recommendations to make
developing your Rails app more productive and joyful.

In this article, we are talking about updating the readme file.

## When

Every time there is some new piece of information that every developer will
need, or that is not obvious or easy to find, add that to the "readme" file.

Setting up a new development machine or onboarding a new developer is a great
time to overhaul your readme file. Change anything that is incorrect, unclear,
or missing.

## Why

Opening an unfamiliar codebase can be very intimidating. A readme file gives
future developers a way to get their bearings. It can't tell you where
everything is, but it can let you know where to start looking – and that is huge.

## How

Your readme file should probably include the name of the app, what it does, how
to set up your development environment, how to run the tests, how to deploy, and any other information a new developer is likely to need.

This should go into a file called `README.md`.

Here is an example readme file:

```markdown
# Hello World

Universal greeter for all human and non-human entities

## Development

Instructions on how to develop go here

### Specs

`rake`

### Deployment

`bin/deploy`

### Updating libraries

`bin/gem_update`
```

## Alternatives

In the long ago time, readme files were named `README.txt` or `README` or
occasionally `Readme`.

The all caps version of the file name makes it very easy to notice in a file
listing.

The `.md` extension indicates that the file is Markdown so it gets rendered
nicely in GitHub and elsewhere.
