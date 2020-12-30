---
title: Add a CSS Framework
description: Make it easy to make your interface beautiful.
published_at: February 16, 2021 7 am PT
category: software
tags: rails joyful_rails
---

{% include joyful-rails-intro.html %}

In this article, we are talking about adding a CSS framework.

## When

When it comes time to make things pretty, use a good CSS framework to make that
easier.

## Why

CSS frameworks exist for the same reasons Rails does. They make a lot of the
decisions for you and give you pre-built components that you can combine and
customize to make your app.

## Options

### Bulma

[Bulma](https://bulma.io) is good and doesn't require any JavaScript.

Many CSS frameworks depend on JavaScript for basic functionality so they make
your application completely unusable when the user does not have Javascript,
when there is an issue downloading the JavaScript, or when there is a bug in the
Javascript. Bulma has no JavaScript so it does not have that problem.

You can [install](https://bulma.io/documentation/overview/start/) it as an NPM
package, load it remotely, download and use the compiled CSS, or download and
use the source Sass. (That last option is unsupported.)

## US Web Design System

[The US Web Design System](https://designsystem.digital.gov) is beautiful,
authoritative, completely accessible, and works with or without Javascript.

Because USWDS was built for Federal agencies, it has extremely high standards for
accessibility. It is highly themeable but still tends towards a very formal,
authoritative look.

It can be
[installed](https://designsystem.digital.gov/documentation/developers/) as an
NPM package or as a source code download. There are several third party
distributions but none suitable for a Rails application. I advise using the NPM
package with Yarn.

## Zurb Foundation

[Foundation](https://get.foundation) is very nice.

It can be [installed](https://get.foundation/sites/docs/installation.html) in
many different ways. However, currently the Rails gem
[foundation-rails](https://github.com/foundation/foundation-rails) has an [issue with Rails 6](https://github.com/foundation/foundation-rails/issues/281)

The workaround appears to include:
1. installing Coffeescript for the duration of the install process.
2. commenting out `@include foundation-button-group;` in
  `app/assets/stylesheets/foundation_and_overrides.scss`.
