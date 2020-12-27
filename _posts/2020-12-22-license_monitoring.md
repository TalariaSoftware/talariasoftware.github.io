---
title: Use a License Monitor
description: Avoid using libraries with licenses you do not want to agree to.
published_at: December 22, 2020 7 am PT
category: software
tags: rails joyful_rails
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of recommendations to make
developing your Rails app more productive and joyful.

In this article, we are talking about using a license monitor.

## When

The longer you wait before adding a license monitor, the more work you will have
to do to correct problems that have accumulated. For that reason, I recommend
adding a license monitor early – and absolutely before you start distributing your
application.

## Why

Rails applications often leverage an extensive network of open
source software distributed under a variety of licenses. It is very important to
avoid using software if you do not agree with the terms of the license.

A license monitor can check the licenses of your libraries and make sure they
only use licenses you agree to abide by.

## How

Use [License Finder](https://github.com/pivotal/LicenseFinder).

### Install

To install, add `gem 'license_finder'` to the development section of your
`Gemfile`.

To run, use the command: `license_finder`.

### Configure

For License Finder to work, it needs to know which licenses are acceptable to you.
Use the `permit` subcommand to record those. Here is an example with
what I think are reasonable defaults:

```sh
bundle exec license_finder permit add MIT MIT* ruby "Apache 2.0" ISC BSD \
"Simplified BSD" "New BSD" BSD-3-Clause 0BSD BSD* Unlicense CC0-1.0 CC-BY-3.0 \
CC-BY-4.0 WTFPL "Brakeman Public Use License"
```

Some packages list multiple licenses in a way that License Finder doesn't
understand. For those, we need to correct which licenses are available.

```sh
bundle exec license_finder licenses add amdefine MIT
bundle exec license_finder licenses add amdefine BSD-3-Clause

bundle exec license_finder licenses add atob MIT
bundle exec license_finder licenses add atob Apache-2.0

bundle exec license_finder licenses add node-forge BSD-3-Clause
bundle exec license_finder licenses add node-forge GPL-2.0

bundle exec license_finder licenses add pako MIT
bundle exec license_finder licenses add pako Zlib

bundle exec license_finder licenses add path-is-inside WTFPL
bundle exec license_finder licenses add path-is-inside MIT

bundle exec license_finder licenses add sha.js MIT
bundle exec license_finder licenses add sha.js BSD-3-Clause
```

Finally, if you followed the advice on [library vulnerability
checks](library_vulnerability_checks) then you installed
[bundler-audit](https://github.com/rubysec/bundler-audit#readme). Bundler-audit
is has a GPL license, which means we can't incorporate it into non-GPL code. But
it is not part of our app – it's only a tool we use – so it's okay.

```sh
bundle exec license_finder approvals add bundler-audit
```

## Caveat

I am not a lawyer and neither is License Finder. None of this will guarantee
that you do not illegally incorporate other people's software into your code.
Nor will it guarantee that you are not creating liabilities or obligations that
you do not want.

If your need legal advise, consult with an attorney licensed to practice in your
jurisdiction.
