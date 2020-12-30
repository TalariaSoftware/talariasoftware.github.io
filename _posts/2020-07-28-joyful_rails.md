---
title: Joyful Rails
description: A guide to make working with your Rails application more productive and joyful.
published_at: July 28, 2020 7 am PT
updated_at: December 29, 2020
redirect_from: /articles/the_annotated_guide_to_a_new_rails_app
category: software
tags: rails joyful_rails
---

## Introduction

I love [Ruby on Rails](https://rubyonrails.org). I think it's a fantastic
framework for web applications. I highly recommend it and I thoroughly enjoy
working with it.

I've been lucky enough to work extensively with Rails on many different projects
over many different years. Most Rails development, like most software
development, happens on long-lived projects. A well-established and
well-configured project is an absolute joy to work in and collaborate on.

But a new Rails project doesn't have many of the little tweaks and additions
that make things so nice for me. I end up spending a lot of time and frustration
repeating the same steps in every application.

This guide is an effort to make those steps faster and easier. The goal is to
create a smooth and rapid path from zero to a codebase I love working in.

### What This Is Not

#### This is not a beginner's guide

I will explain things as simply as I can, but there will likely be some
important information left out. If you do not understand a recommendation, you
might not understand the consequences.

#### This is not something to apply blindly

Examine every bit of the advice herein to see if it is right for you, your
project, and your team before applying it. That's what the annotations are for.

#### This is not static

The world changes and I change with it. My preferences and recommendations are
in constant flux. This guide will change with them.

#### This is not an automated setup script

There is no point in automating something that will change every time you do it.

If you want an automated setup script, take a look at
[Suspenders](https://github.com/thoughtbot/suspenders). It is a Rails template
created by Thoughtbot with their standard defaults. They make a lot of good
choices, some of which I will certainly draw from.

## Table of Contents

{% assign chapters = site.tags.joyful_rails | reverse %}


{% for chapter in chapters %}
### {% increment counter %} <a href="{{ chapter.url }}">{{ chapter.title }}</a>

{{ chapter.description }}

{% endfor %}

<!--
Todo:
- Footer at the bottom
- StimulusJS Hello world
-->
