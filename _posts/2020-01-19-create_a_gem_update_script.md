---
title: Create a Gem Update Script
description: Update your application libraries with ease.
published_at: January 19, 2021 7 am PT
category: software
tags: [rails]
---

{% include joyful-rails-intro.html %}

In this article, we are talking about creating a gem update script.

## When

I recommend creating a gem update script the first or second time you update the
gems in your project.

I recommend updating your gems often. Every day or week that you are writing
code is a good choice. For projects in active use but not in active development,
every month is a good choice.

## Why

Having a single command to update gems makes it easy to update them often.

Updating your gems often will make sure that you are using the latest versions
of libraries, versions where known bugs, security vulnerabilities, and other
problems are fixed.

## How

Put the following code into the file `bin/update_gems`.

```sh
#!/bin/bash
set -e

test -z "$(git status --porcelain)" || (echo "Git repo not clean"; exit 1)

bundle update
rake
git commit -am "Updated gems"
```

Don't forget to make your gem update script executable.

```sh
chmod +x bin/update_gems
```

Now you can update all of your gems with a single command: `./bin/update_gems`.
