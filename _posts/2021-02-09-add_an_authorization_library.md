---
title: Add an Authorization Library
description: Identify what users can do.
published_at: February 9, 2021 7 am PT
category: software
tags: rails joyful_rails
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of recommendations to make
developing your Rails app more productive and joyful.

In this article, we are talking about adding an authorization library.

## When

After you add [authentication](add_authentication) to your application, you will
probably start writing code that does different things depending on who the user
is.

That is a good time to add an authentication library to make creating, testing,
and maintaining that code much easier.

## Why

If have user authentication, your app knows who its users are. That's great!

But you probably wanted to know who the users are so that you can allow them to
do different things.

Determining what a user can do is the process of authorization.

What usually happens is you end up with code that looks like this:

```ruby
if user.present? && post.author == user
  post.update body: new_body
end
```

This is tricky to write, tricky to test, and ends up spread all over your app.

An authentication library helps you put that code all in one place, making it
easy to understand, test, and maintain.

## How

Use [Pundit](https://github.com/varvet/pundit#readme).

## Alternatives

[Cancan](https://github.com/ryanb/cancan#readme) is another option and I am sure
there are many more. I like Pundit enough that I haven't explored any
others.
