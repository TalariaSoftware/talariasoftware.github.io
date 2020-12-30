---
title: Create a Deploy Script
description: Deploy your application libraries with ease.
published_at: January 12, 2021 7 am PT
category: software
tags: [rails]
---

{% include joyful-rails-intro.html %}

In this article, we are talking about creating a deploy script.

## When

As soon as you have a [production environment]() you should create a deploy
script.

## Why

Having a single command to deploy makes it easy to deploy often and ensures that
you don't forget or miss any of the deploy steps.

A deploy script should:
- Run all automated tests
- Make sure the code being tested is the code actually being deployed
- Deploy the updated code
- Run migrations if necessary

## How

Put the following code in the file `bin/deploy`.

```sh
#!/bin/bash
set -e

heroku whoami > /dev/null || (echo "Not logged into heroku. Run \`heroku login\`."; exit 1)
test -z "$(git status --porcelain)" || (echo "Git repo not clean"; exit 1)

rake

git push origin
git push https://git.heroku.com/heroku_app_name.git develop:main
heroku run rake db:migrate --app heroku_app_name
```

Replace `heroku_app_name` with the name of your Heroku application.

Replace `develop` with name of the branch you want to deploy from.

Don't forget to make your deploy script executable.

```sh
chmod +x bin/deploy
```

Now your entire deploy process can be run with a single command: `./bin/deploy`.

## Alternatives

Deploy scripts should be specific to the team using them and the environment
they are deploying to. If your deployment process is different, then your deploy
script will need to be different.

The point is to automate as much as possible to ensure that that you can deploy
quickly, easily, and correctly.
