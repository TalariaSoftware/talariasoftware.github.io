---
title: "Hotwire: First Reactions"
description: All the benefits of client-side SPA frameworks, with almost none of the downsides.
published_at: December 26, 2020 9:00:00 -0800
updated_at: Dec 30, 2020
category: software
tags: [rails, hotwire, SPA]
---

[Hotwire](https://hotwire.dev) is a set of libraries and conventions that does for
single-page interactivity on websites what Rails did for web applications.

It provides all the benefits of client-side single-page application (SPA)
frameworks with almost none of the downsides.

It does that by making HTML primary and providing a standard set of JavaScript
tools to update and augment the HTML on the page.

## Benefits of an SPA

All the benefits of a single-page app come down to different aspects of the same
thing: reactivity./*I find "responsiveness" better than "reactivity" in this use. Will mark other places.*/

When the user performs an action, the application reacts /*responds*/immediately, without
the delay of an HTTP request, page download, render, and state reset.

When there is a change in application state that is not initiated by the user,
the change is immediately visible to the user without needing to click, reload,
or wait for the page to download and re-render.

## Downsides of an SPA

The downside of SPAs is that they are complicated. That complexity results in
several times more work for developers, while simultaneously breaking
functionality that is included automatically with HTML pages.

SPAs are not web applications. They are JavaScript applications that users
download and run in their web browsers.

Users have to wait for the JS bundles to download and initialize before the
application first begins to render. Then, while using the app, they find that the
web browser navigation buttons (back, reload, forward, etc.) cause the app to
break or reset. URLs cannot be used to point to specific parts of the
application, making bookmarks useless. Worse still, keyboard navigation, screen
readers, and other assistive technology are often broken. And if you are running
an uncommon browser or older hardware, you may not be able to use the app at
all.

All of this could be fixed or mitigated with sufficient care and effort from the
developers, but none of that work is necessary for web applications serving HTML
and CSS.

Meanwhile, developers are also dealing with other added complications.

Behavior and views rendered by the server need to be duplicated by the front-end
JavaScript code. There is a entire set of technologies to maintain for the front
end with their own languages, libraries, compile chains, and distribution
processes for running in a wide array of environments. And then there is the
extra abstraction layer, usually JSON, between content on the back end and the
HTML and CSS rendered for users.

## Introducing Hotwire

Hotwire was [released](https://twitter.com/dhh/status/1341420143239450624) on
December 22, 2020 by [DHH](https://twitter.com/dhh/) and the rest of the team at
[Hey](https://hey.com). It was extracted from Hey in the same way that Rails was
extracted from Basecamp.

There are two main libraries that make up Hotwire: Turbo and Stimulus.

### Turbo

[Turbo](https://turbo.hotwire.dev) is the next evolution of
[Turbolinks](https://github.com/turbolinks/turbolinks).

Turbolinks uses JavaScript to replace the body of an HTML page. By avoiding a
page reload, it makes navigating web apps faster. It does this with no custom
JavaScript and, in most cases, is fully transparent to users and developers.

Turbo takes the strategy a step further and provides tools to update parts of
the page in response to user action or live updates broadcast over a WebSocket.

### Stimulus

Stimulus is the modest JavaScript framework focused on augmenting the HTML already
on the page. It provides a guided way to add dynamic client-side behavior
without changing the way HTML and CSS pages are built and rendered.

Together, Turbo and Stimulus make it possible to have web apps that behave like
JavaScript applications but are primarily HTML and CSS with minimal
application-specific JavaScript. They offer all the benefits of an SPA, with almost
none of the downsides.

## How Hotwire works

Probably more important than the libraries that make up Hotwire are the
conventions on how those libraries interact.

The most important of these conventions is the one that gives Hotwire its name:
HTML Over-The-Wire.

Traditional SPAs send JSON to the client. The JavaScript app then takes that
JSON and generates HTML that is rendered onto the page.

When you send HTML over-the-wire, you don't need all the JavaScript code that
knows how to render it to HTML. It also means that you don't need to duplicate
your templates or template rendering. The same server-side code generates the
HTML that the user sees, no matter how it gets onto the page.

## Downsides of Hotwire

There is no silver bullet; even Hotwire has its downsides.

### New Technology

Hotwire is a new framework. It hasn't been proven in a lot of applications and
no one outside of Basecamp has a lot of experience with it.

However, Stimulus is proven technology that's been around for years. Turbo
evolved from Turbolinks which has been a part of Rails since 2012.

And all of Hotwire is in production at Hey.

### Convention Dependent

Hotwire with Rails is built on an extensive set of conventions that allow the
different parts to work together. If you do not follow these conventions
carefully, you will end up with a hairy mess of spaghetti code.

Once these conventions are well-understood and strongly modeled, they are easy
to follow; but until then, there is a significant risk of making your code
confusing and buggy.

### Complicated

Hotwire is a huge improvement over SPA frameworks, but it is still complicated
--- really complicated.

### Integration Specs Require JavaScript

It seems the only way to write specifications that demonstrate your Hotwire
functionality is working as intended is to use Capybara with a
JavaScript-capable web browser. This is orders of magnitude slower than the
Rack-based browser used when you don't need to test JavaScript integration.

Other SPA frameworks have the same problem. The best way to mitigate it is with
strong, simple conventions that give you a lot of confidence that the
integration works, so few integration specs are needed.

## Conclusions

Hotwire provides an HTML/CSS-centric way of creating live and reactive web
applications. I believe it will revolutionize reactive web apps the same way
Rails revolutionized web apps.

I highly recommend learning about it and adding it to your tool belt. Anytime
you want to improve a portion of your web app by making it more instant and
reactive, Hotwire is the tool to reach for.

The smart thing to do is add Hotwire little by little to places where it will
have the biggest impact. But the technology is so exciting, I am considering
rewriting entire applications to take full advantage of it.

---

If you are interested in other ways to make developing your Rails application
awesome, take a look at [Joyful Rails](/articles/joyful_rails).
