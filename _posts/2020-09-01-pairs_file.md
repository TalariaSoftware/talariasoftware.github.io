---
title: Pairs File
description: Accurately record changes made while pairing by adding multiple authors to your commits.
published_at: September 1, 2020 7 am PT
category: software
tags: rails joyful_rails
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of
recommendations to make developing your Rails app more productive and joyful.

In this article, we are talking about the "pairs" file.

## When

The "pairs" file is helpful when you are doing a lot of pair-programming and want
to be able to easily assign multiple authors to your git commits.
## Why

Having an accurate record of authors is useful when a developer needs to
understand a section of code. This becomes especially important when the project
is large, long-lived, and developed by a large team.

## What

[Pivotal's git scripts](https://github.com/pivotal-legacy/git_scripts) make it
easy to assign multiple authors to a commit.

## How

Install the Pivotal git scripts:

`gem install pivotal_git_scripts`

Create a `.pairs` file in the root directory with your team's information:

```yaml
pairs:
   gh: Grace Hopper; g.hopper@example.mil
   al: Ada Lovelace; countess.lovelace@example.co.uk
   mh: Margaret Hamilton; margaret@nasa.example.gov
```

Then use the new Git subcommand to set the author(s) before making your commits.
For example, if Grace and Margaret were working together, they would run the
command with their initials like this:

`git pair gh mh`
