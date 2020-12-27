---
title: Switch to PostgreSQL
description: Switch over to a production-ready database.
published_at: September 22, 2020 7 am PT
category: software
tags: [rails]
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of
recommendations to make developing your Rails app more productive and joyful.

In this article, we are talking about switching to PostgreSQL.

## When

I recommend switching to PostgreSQL before creating your first production
environment.

## Why

Rails uses SQLite as the database by default because it is fully-contained;
there is no server to manage and the data is kept in a local file.

However, SQLite is not suitable for most production environments;
[PostgreSQL](https://www.postgresql.org) is a much better choice.

PostgreSQL should also be used in development in order to maintain [dev/prod
parity](https://12factor.net/dev-prod-parity).

## How

To switch to PostgreSQL:

1. Install PostgreSQL on your development machine and make sure that it is
   running.
2. Change the database gem. In `Gemfile`, replace `gem 'sqlite3'` with `gem
   'pg'`. Then run `bundle` to update your gems.
3. Change the database adapter. In `config/database.yml` replace the adaptor:
   `adapter: sqlite3` with `adapter: postgresql`.
4. Change the database names in `config/database.yml`. Use
   `projectname_development` for the development database, `projectname_test`
   for the test database, and `projectname_production` for the production
   database.

Test that this works by running `rake db:create`.

## Alternatives

Large and successful projects are also run on MySQL. In the past, MySQL had some
severe limitations but those issues may be papered over by Rails or fixed
entirely.

I wouldn't risk it, but others certainly do.
