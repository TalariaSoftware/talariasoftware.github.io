---
title: Add a License
description: If your code is open source, make sure people know.
published_at: September 8, 2020 7 am PT
category: software
tags: [rails]
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of
recommendations to make developing your Rails app more productive and joyful.

In this article, we are talking about adding a license.

## When

When you want to allow other people to use your code, use a license file to make
it clear that they can.

## Why

You (or your employer) own the copyright of the code you write. Using your code
involves making and distributing copies of the code and derivatives thereof. In
order for other people to do that legally, they need permission from the
copyright owner.

A license file tells them what permissions you are granting them and under what
conditions.

## How

Consider using the [Hippocratic License](https://firstdonoharm.dev).

Put a copy of the license in a file called `LICENSE` in the root folder of your
git repository.

## Alternatives

There are dozens of widely used open-source licenses with various terms for
things like credit, source-code availability, or even, in the case of the
Hippocratic License, a commitment to not violate human rights.

There are even licenses that are actually dedications to the public domain,
renouncing the author's copyright entirely.

The license you choose should reflect your values and goals. No matter what
those are, there is probably a license that supports them.

Please do not write your own open-source license. Software licenses are legal
documents that require extensive expertise to read and write. Even if you do
manage to create something that does what you intend, each of your users will
have to invest extra effort to be certain of what it does and all its
repercussions.
