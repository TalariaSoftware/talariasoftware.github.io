---
title: Types of Specifications
description: The five types of specifics present in all software projects
published_at: Jun 21, 2016 1:30 pm Pacific Time
---

## What is a specification?

Before we can talk about specifications we have to know what they are.

Specification is a noun, derived from the verb to specify. To specify is to
state explicitly or in detail. Therefore a specification is the result of
stating explicitly or in detail, or something that states explicitly or in
detail.

Every software team has their own unique points of view, cultural wisdom, and
shared practices regarding specifications but they can be grouped into a few
categories.

## No specifications

“We don’t have have specifications, that’s too much overhead. That’s fine if
you’re at NASA or Chase but we’re a lean mean startup that has to add features
fast.”

“What feature are you working on now?”

“I’m adding a subscription option that gives users a regular allotment of
credits.”

“That’s a specification.”

It is not possible to have no specifications. If you don’t know what a method
does how could you possibly know how to write it? If you don’t know what your
application is supposed to do, how do you make it do that?

## Implicit specifications

“Yeah, we know what the software is doing, but it’s not like we have any actual
specification document.”

“You have implicit specifications.”

An implicit specification is any specification that doesn’t exist outside of
someone’s head.

Implicit specifications have a lot of upsides. They are very easy to create,
springing into existence with no little or no effort. They are equally easy to
change, as fluid as thought itself.

This flexibility is also the downside of implicit specifications. When the
behavior changes constantly and without warning it is very difficult to
effectively use the software. When the specification changes constantly it’s
difficult to write code that meets the it; you are trying to hit a moving
target.

Large, complicated, or confusing specifications exasperate the problem. When
implicit, these specifications change for no other reason than it is not
possible to maintain them completely in working memory.

Keeping specifications implicit also makes it easy to overlook problems such as
ambiguity, incompleteness, or inconsistency.

Finally, implicit specifications are impossible to communicate. To express them
in language is to make them explicit. If the communication is not captured, for
example a water-cooler conversation, then the explicit specification is lost
forever and what you have left is multiple implicit specifications.

## Plain English specification

“In order to avoid those type of confusions we write our specs down.”

“What spec are you working on implementing now?”

“I’ll read it to you, ‘Ensure subscribers each have 100 credits biweekly.’”

A plain English specification is a specification written in plain
English.<sup>[0](#footnote0)</sup>

One of the curious characteristics of English is that it is ambiguous and
imprecise. For example, does this happens twice a week or every two weeks? Do
subscribers get their credit balance set to a total of 100 no matter what the
previous value was or is it incremented 100 more than the previous balance?

## Legalese specifications

“We work very hard to avoid ambiguity in our specs.”

“Oh? What spec are you working on now?”

“It says, ‘Whereas a user has paid a monthly subscription fee, when the month
or mid-month period has ended, and the subscriber has at least -- ‘”

"-- never mind."

Eliminating ambiguities and ensuring precision in language is the same work
a lawyer does when writing a contract or other legal document. The outcomes are
are also very similar. I call these legalese specifications.

Even for experts, writing and reading legalese takes considerable effort. And
after all their training, experience, expertise, and effort, the existence of
courts demonstrates that legalese is still not always as precise or unambiguous
as needed.

## Executable specifications

An executable specification is computer code that specifies how another
computer program works.

Executable specifications are precise and unambiguous by their nature as
computer code.

Executable specifications are very useful to keep for regression testing.
A computer can test your application in seconds or minutes against
a specification that a human would spend days or weeks on.

## Recommendations

You can’t actually do without specifications. My recommendation is that you
write them down and that you write them as computer code. Executable software
is the only effective way to describe the behavior of executable software.

Write your specifications, in executable software, and then use that software
to drive your development.

I call it specification-driven development.

<hr/>

<a name="footnote0"><sup>0</sup></a>Everything I say about plain English
specifications is most likely true about specifications written in any natural
language.
