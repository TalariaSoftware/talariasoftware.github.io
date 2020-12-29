---
title: Default Rake Task
description: Run all of your automated checks with a single command.
published_at: December 29, 2020 7am PT
category: software
tags: rails joyful_rails
---

This is part of [The Annotated Guide to a New Rails
App](the_annotated_guide_to_a_new_rails_app), a list of recommendations to make
developing your Rails app more productive and joyful.

In this article, we are talking about adding to the default rake task.

## When

I recommend adding to the default rake task every time you add a tool that
automatically checks your codebase.

## Why

Having a single command to run all of your automated checks and specs makes it
easy to run them after every change and before every deploy.

## How

First, create Rake tasks for automated checkers that do not have one.

### Rubocop

In `lib/tasks/rubocop.rake` put

```ruby
if Gem::Specification.find_all_by_name('rubocop').present?
  require 'rubocop/rake_task'
  RuboCop::RakeTask.new
end
```

Now you can run `rake rubocop`.

### Bundler audit

In `lib/tasks/bundler_audit.rake` put

```ruby
if Gem::Specification.find_all_by_name('bundler-audit').present?
  require 'bundler/audit/task'
  Bundler::Audit::Task.new
end
```

Now you can run `rake bundle:audit`.

### License Finder

In `lib/tasks/license_finder.rake` put

```ruby
task license_finder: :environment do
  sh 'license_finder', '--quiet'
end
```

Now you can run `rake license_finder`.

### Rails Best Practices

In `lib/tasks/rails_best_practices.rake` put

```ruby
task rails_best_practices: :environment do
  sh 'rails_best_practices'
end
```

Now you can run `rake rails_best_practices`.

### Brakeman

In `lib/tasks/brakeman.rake` put

```ruby
if Gem::Specification.find_all_by_name('brakeman').present?
  namespace :brakeman do
    desc "Check your code with Brakeman"
    task check: :environment do
      require 'brakeman'
      r = Brakeman.run app_path: '.', print_report: true, pager: false
      exit Brakeman::Warnings_Found_Exit_Code unless r.filtered_warnings.empty?
    end
  end
end
```

Now you can run `rake brakeman:check`.

### Default rake task

Edit your `Rakefile` define the default rake task.

```ruby
task default: %i[
  rubocop
  spec
  rails_best_practices
  license_finder
  brakeman:check
  bundle:audit
]
```

To run the default task with all of your automated checks and specs use this
command: `rake`.
