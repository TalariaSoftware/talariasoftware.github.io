---
title: Switch to HAML
description: Make your HTML templates easier to work with.
published_at: October 6, 2020 7 am PT
category: software
tags: rails joyful_rails
---

{% include joyful-rails-intro.html %}

In this article, we are talking about switching to HAML.

## When

I recommend switching to HAML before investing significant effort into your
HTML.

## What

HAML is an HTML templating language. It makes it easier and more pleasant to
write HTML templates.

## Why

The default templating language for Rails is ERB (aka eRuby or Embedded Ruby).
It is a simple way to embed Ruby code into text files using expression tags
(<%= '<code>&lt;%= %&gt;</code>'.html_safe %>) and execution tags (<%=
'<code>&lt;% %&gt;</code>'.html_safe %>).

[HAML](https://haml.info) is a templating language that makes the HTML structure
clear and easy to work with by using meaningful whitespace and eliminating
unnecessary characters.

## How

Add `gem 'haml-rails'` to your `Gemfile` and run `bundle`.

[Replace all your ERB
views](https://github.com/haml/haml-rails#converting-all-erb-views-to-haml-format)
with HAML views by running `HAML_RAILS_DELETE_ERB=true rails
haml:erb2haml`.
