---
title: Configure Generators
description: Make the Rails generators generate the code you want. No more, no less.
published_at: November 3, 2020 7 am PT
category: software
tags: rails joyful_rails
---

{% include joyful-rails-intro.html %}

In this article, we are talking about configuring the Rails generators.

## When

When or if to configure the Rails generators depends on how much you like the
default generators and how much you use or want to use the generators.

If you like the how the generators work (or you never use them), there is no point
to configuring them. If you don't like what the generators do, and you use them
often or want to use them often, it is a good idea to configure them.

## Why

By default, Rails generators create helpers. Helpers are generally a bad idea;
most helper functions should be part of a model or view object instead.

By default, Rails generators create a stylesheet for every controller.
Stylesheets should not be tied to a controller.

By default, Rails generators create specs for views. Views should not be complicated enough to need specs.

By default, the Rails generators create request specs to test controllers.
Request specs are probably a good idea for APIs, but for more traditional web
apps, it makes more sense to test the controller directly by looking at
the resource assigned and any side effects.

## How

Add the following to the `config/application.rb` file.

```ruby
config.generators.helper = false
config.generators.stylesheets = false
config.generators.view_specs = false
config.generators.request_specs = false
config.generators.controller_specs = true
```

After making a commit, test that this works by running `rails generate resource foo`.

You should get a migration, a model, a controller, a route, a model spec, and
a controller spec. You should not get a helper, stylesheet, view spec, or
request spec.

Remove the files created by the generator.
