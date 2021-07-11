---
layout: default
hero:
  image: /images/hero.png
  callout: Joyful Rails
  button:
    href: /articles/joyful_rails
    text: Read for FREE
  link:
    text: Link to more about that priority
    href: /link/
  content: |
    A guide to make working with your Rails application more productive and
    joyful.

    Step-by-step instructions on dozens of ways to make developing in Rails
    faster and easier.
---

<section class="usa-graphic-list usa-section usa-section--light">
  <div class="grid-container">
    <div class="usa-graphic-list__row grid-row grid-gap">
      <div class="usa-media-block tablet:grid-col">
        <i class="far fa-hammer usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Build Your App</h2>
          <p>You have a vision for an application.</p>
          <p>You are ready to invest to make that dream into a reality, to build
          your product and your business.</p>
          <a class="usa-button usa-button--secondary"
          href="consulting/build_your_app">Get Started </a>
        </div>
      </div>
      <div class="usa-media-block tablet:grid-col">
        <i class="far fa-handshake usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Partnerships</h2>
          <p>You have a production application generating revenue.</p>
          <p>You need a technical partner who can make sure that is stays
          up-to-date, secure, and reliable for your paying customers.</p>
          <a class="usa-button usa-button--secondary"
          href="/consulting/partnerships">Team Up</a>
        </div>
      </div>
      <div class="usa-media-block tablet:grid-col">
        <i class="far fa-notes-medical usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Rails Rescue</h2>
          <p>You have a Rails codebase.</p>
          <p>You need experts to help make your application to be more reliable,
          more maintainable, or more secure.</p>
          <a class="usa-button usa-button--secondary"
          href="/consulting/rails_rescue">Get Help</a>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="usa-graphic-list usa-section usa-section--dark">
  <div class="grid-container">
    <h1>Recent Articles</h1>
    <div class="usa-graphic-list__row grid-row grid-gap-6">

      {% for post in site.posts limit: 4 %}
        <a href="{{ post.url }}" class='usa-media-block tablet:grid-col-6 padding-3'>

          {% if post.layout == 'facebook_video' %}
            <i class='fab fa-youtube usa-media-block__img font-sans-3xl'></i>
          {% elsif post.layout == 'youtube' %}
            <i class='fab fa-youtube usa-media-block__img font-sans-3xl'></i>
          {% elsif post.layout == 'fireside_fm' %}
            <i class='fas fa-microphone-alt usa-media-block__img font-sans-3xl'></i>
          {% elsif post.layout == 'anchor_fm' %}
            <i class='fas fa-microphone-alt usa-media-block__img font-sans-3xl'></i>
          {% else %}
            <i class='fas fa-pen-nib usa-media-block__img font-sans-3xl'></i>
          {% endif %}

          <div class='usa-media-block__body'>
            <h2 class='usa-graphic-list__heading'>
              {{ post.title }}
            </h2>

            <p>{{ post.description }}</p>
            <p>{{ post.date | date_to_string: "ordinal", "US" }}</p>
          </div>
        </a>
      {% endfor %}
      <a class="usa-button usa-button--secondary margin-x-auto" href="/articles">All Articles</a>
    </div>
  </div>
</section>

<section class="usa-section usa-section--light">
  <div class="grid-container">
    <div class="grid-row grid-gap">
      <div class="tablet:grid-col-4">
        <img class="height-15" src="/images/foot-color.png" alt='logo' />
        <h2 class="text-primary font-heading-lg margin-top-0 tablet:margin-bottom-0">
          Build Software.
        </h2>
        <h2 class="text-secondary font-heading-lg text-light text-uppercase margin-top-0 tablet:margin-bottom-0">
          Delight Customers.
        </h2>
      </div>
      <div class="tablet:grid-col-8 usa-prose">
        <p>Software is a means to an end. Your real goals are to delight your customers, grow your business, and make people's lives better. Building software is only valuable when it helps you do those things.</p>
        <p>In order to do that you need to your software to adapt quickly to changes in your environment and in your understanding. And you need to do that in a way that is sustainable because you are in this for the long haul.</p>
      </div>
    </div>
  </div>
</section>
<section class="usa-graphic-list usa-section usa-section--dark">
  <div class="grid-container">
    <div class="usa-graphic-list__row grid-row grid-gap">
      <div class="usa-media-block tablet:grid-col">
        <i class="fas fa-clock usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Build Quickly</h2>
          <p>Develop your products rapidly in order to get to market faster and find product-market fit sooner.</p>
        </div>
      </div>
      <div class="usa-media-block tablet:grid-col">
        <i class="fas fa-money-bill usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Build Efficiently</h2>
          <p>Save time and money with sustainable practices that ensure you can keep moving forward at a steady pace.</p>
        </div>
      </div>
      <div class="usa-media-block tablet:grid-col">
        <i class="fas fa-laugh-beam usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Delight Customers</h2>
          <p>Create products that your customers will love through continual, sustainable feedback and adjustment.</p>
        </div>
      </div>
    </div>
  </div>
</section>
