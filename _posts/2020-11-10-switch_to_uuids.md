---
title: Switch to UUIDs
description: Database keys that can't be guessed, don't overflow, and don't leak information.
published_at: November 10, 2020 7 am PT
updated_at: Dec 2, 2020
category: software
tags: [rails]
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of
recommendations to make developing your Rails app more productive and joyful.

In this article, we are talking about switching the database primary keys to
UUIDs, universally unique identifiers.

## When

On one hand, it is not trivial to change a table's primary key from the default
integer to UUIDs. For that reason, it is helpful to switch to UUIDs as early as
possible.

On the other hand, the benefits of using UUIDs are generally not an important
concern for new applications, so there is little reason to do it right away.

## Why

By default, Rails uses integers as primary keys. Using UUIDs can help prevent a
few problems.

### Integer overflow

Integer primary keys increase monotonically for every new row. Eventually, the
primary key gets too large and new entries cannot be created.

Since Rails 5.1 the default is to use 64-bit integers, which means this will
not be a problem until you've created over `9*10^18` rows.

UUIDs are much larger (128-bits total) and chosen randomly. So even when
you have over `9*10^18` rows your primary key will not be the problem.

### Guessable primary keys

Every new integer primary key is one more than the previous one, which means it
is trivial to guess what IDs have been created and which ones will be created
next.

Knowing what primary keys exist should not be a security issue by itself, but
you may still want to hide as part of a defense in depth.

### Estimable creation rates

Every new integer primary key is one more than the previous one, which means it
is simple to find out how quickly they are being created.

That information may reveal how many users signed up yesterday or how many
orders were created this week.

For most applications, most of the time, no one cares and this is not an issue.
If it might be for you, using UUIDs as your primary keys can eliminate it.

## How

### Enable UUIDs in PostgreSQL:

We assume you have already made the [switch to
PostgreSQL](switch_to_postgresql).

1. Generate a migration: `rails generate migration EnableUuids`.
2. Put this in the change method of the migration: `enable_extension 'pgcrypto'`
3. Run the migration: `rake db:migrate`

### Configure the generators to use UUIDs as primary keys:

In `config/application.rb` add `config.generators.orm :active_record,
primary_key_type: :uuid`.

### Test the change

After making a commit, test that this works by running `rails generate model
foo` and `rake db:migrate`.

The migration and schema should both indicate that the id is a UUID.

Run `rake db:rollback` and remove the generated files before continuing.

## Gotchas

When creating a foreign key column (using `references` or `belongs_to`) you must
indicate the type if the id is a UUID.

For example:

```ruby
create_table :post, id: :uuid do |t|
end

create_table :comment, id: :uuid do |t|
  t.belongs_to :post, type: :uuid
end
```
If you do not do this, there is a risk of silent errors when the UUIDs are
coerced into an integer to fit into a column that expects an integer.
